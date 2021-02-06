# CASA-NASA-HUNCH-2020-2021
Repository for CASA's 2020-2021 Nano Ag Lab project

## Environmental Combo Sensor
Sparkfun had examples of code for running both the bme280 sensors and ccs811 sensors, but we wanted to run both at the same time, so we made some example code based on the example code written by kirk-sfe at SparkFun. The installation instructions for the python packages were written by them as well.

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
