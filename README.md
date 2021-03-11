# README

The purpose of this README is to give guidelines for developing applications with Terabee 3Dcam 80x60 using the OpenNI 2 framework on Linux. 

For more information about the Terabee 3Dcam 80x60, please click [here](https://www.terabee.com/shop/3d-tof-cameras/terabee-3dcam/).

## System Requirements

* Ubuntu 16.04 or 18.04

## Prepare software development environment

### Install OpenCV

In order to use the SDK, installing OpenCV with the right version is **mandatory**.

Please install OpenCV **3.4.1**.

You can find more information on how to do so [here](https://docs.opencv.org/3.4.1/d7/d9f/tutorial_linux_install.html).


### Install USB-1.0 library

```
sudo apt-get install libusb-1.0-0
```

### Install Terabee 3Dcam SDK

* Download the Linux SDK from the Downloads section of Terabee 3Dcam [here](https://www.terabee.com/shop/3d-tof-cameras/terabee-3dcam/).

* Extract the content of the archive (relevant to your system architecture and desired OpenNI version) in the directory of your choice

* Enter the SDK folder and install the SDK with root permission
```
sudo ./install.sh
```

## Start developing your application

To get started with your application development, we provide sample codes to help you initiate your development. The following steps provide instructions on how to download and run sample codes. 

### Install Git

If Git is not installed on your computer you can install it using the following command:

```
sudo apt-get install git-core
```

### Clone sample code
Clone the project into the SDK folder.

```
git clone https://github.com/Terabee/linux_openni2_samples.git Terabee_samples
```

### Build Samples
#### DepthViewer

This sample will show you how to access camera data and display it into a window.

To compile it, use the following commands:

```
cd Terabee_samples/DepthViewer
cp -r ../../Redist/* .
cp ../../Tools/OpenNI2/Drivers/libmodule-terabee2.so OpenNI2/Drivers/
CXX=g++ make
```
Now to run the program, just use the following command:
```
./Bin/DepthViewer
```

### Build your own application

Taking as example the sample we provide, you can start to develop your own application. Depending on your case, you will need to adapt some items in the Makefile. For instance:

* Append the source files name to SRC
* According the path related to SDK, modify the CPPFLAGS and LDFLAGS appropriately. i.e., you may need to add -I and -L to the correct location.

#### Redist folder

In order to run your custom application, you have to copy:
* the content of the **Redist** folder (available in the SDK folder) to your execution folder.
* the Terabee module driver library (libmodule-terabee2.so) from **\<SDK folder\>/Tools/OpenNI2** to **DepthViewer/OpenNI2/Drivers** you just copied from inside the **Redist** folder.
