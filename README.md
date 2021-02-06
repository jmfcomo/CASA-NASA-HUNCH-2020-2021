# CASA-NASA-HUNCH-2020-2021
Repository for CASA's 2020-2021 Nano Ag Lab project

## Environmental Combo Sensor
Sparkfun had examples of code for running both the bme280 sensors and ccs811 sensors, but we wanted to run both at the same time for the project, so we made some code based on the example code written by kirk-sfe at SparkFun. The installation instructions for the python packages were written by them as well.

Uses python packages: sparkfun-qwiic-bme280 and sparkfun-qwiic-ccs811, developed by SparkFun Electronics

### PyPi Installation
This repository is hosted on PyPi as the [sparkfun-qwiic-bme280](https://pypi.org/project/sparkfun-qwiic-bme280/) package and the [sparkfun-qwiic-ccs811](https://pypi.org/project/sparkfun-qwiic-ccs811/) package. On systems that support PyPi installation via pip, these libraries are installed using the following commands

For all users (note: the user must have sudo privileges):
```sh
sudo pip install sparkfun-qwiic-bme280
```
```sh
sudo pip install sparkfun-qwiic-ccs811
```
For the current user:

```sh
pip install sparkfun-qwiic-bme280
```
```sh
pip install sparkfun-qwiic-ccs811
```

### Local Installation
To install, make sure the setuptools package is installed on the system.

Direct installation at the command line:
```sh
python setup.py install
```

To build a package for use with pip:
```sh
python setup.py sdist
 ```
A package file is built and placed in a subdirectory called dist. This package file can be installed using pip.
```sh
cd dist
pip install sparkfun_qwiic_bme280-<version>.tar.gz
```
### Running the Environmental Combo Sensor
```python
#Copyright 2019 SparkFun Electronics

#Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

#The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

#THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

import qwiic_bme280
import qwiic_ccs811
import time
import sys

def runSensors():

	myBME280 = qwiic_bme280.QwiicBme280()
	myCCS811 = qwiic_ccs811.QwiicCcs811()
	
	if my BME280.is_connected() == False:
		print("The Qwiic BME280 device isn't connected to the system. Please check your connection", \
			file=sys.stderr)
		return

	myBME280.begin()

	if my CCS811.is_connected() == False:
		print("The Qwiic CCS811 device isn't connected to the system. Please check your connection", \
			file=sys.stderr)
		return

	myCCS811.begin()

	while (myBME.is_connected() and myCCS811.is_connected()) == True:
		print("Humidity:\t%.3f" % myBME280.humidity)

		print("Pressure:\t%.3f" % myBME280.pressure)	

		print("Altitude:\t%.3f" % myBME280.altitude_feet)

		print("Temperature:\t%.2f" % myBME280.temperature_fahrenheit)

		print("CO2:\t%.3f" % myCCS811.CO2)

		print("TVOC:\t%.3f" % myCCS811.TVOC)

		print("")
		
		time.sleep(1)

runSensors()
