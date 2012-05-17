jzmq libraries for Android
==========================

This package is intended to easily cross-compile the jzmq shared object and java 
sources for use within Android. 

You will end up with the genrated Java source files for jzmq and a shared library object,
namely libjzmq.so whil will self-contain jzmq wrapper, zeromq library and libtool dependency.

Hence, you can use it directly inside your APK for loading.


Automatically downloaded packages
---------------------------------
> e2fsprogs-1.43.1

> zeromq-2.2.0

> zeromq-jzmq-1.0.0

All of them, stable version.



Building steps
--------------

### Build the NDK ARM toolchain

* Download the NDK from Google.
* In the uncompressed folder, execute

> sh build/tools/make-standalone-toolchain.sh

* It builds a toolchain that you will have to uncompress somewhere

> cd /opt

> tar vjxf arm-linux-androideabi-4.4.3.tar.bz2

* You now have the path /opt/arm-linux-androideabi-4.4.3 as toolchain path.

### Download the JDK from Oracle
* Download and install a JDK from Oracle.
* A 32-bit JDK-1.6.30 is recommended.

### Setup your environment

> export JAVA_HOME=$HOME/work/bin/jdk1.6.0_30

> export ARM_TOOLCHAIN=/opt/arm-linux-androideabi-4.4.3

> export INSTALL_PATH=/opt/android-jzmq/output-arm

### Install the prerequisites

> sudo apt-get install autoconf automake libtool

### Make

> make all

or, if your $INSTALL_PATH is not directly writeable,

> sudo make all

