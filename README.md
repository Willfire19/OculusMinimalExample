OculusMinimalExample
==================

Example code for using the Oculus Rift

# Instructions for building (all platforms)

## Checking out 

	git clone https://github.com/jherico/OculusMinimalExample.git --recursive

## Creating project files

	cd OculusMinimalExample
	mkdir build && cd build
	cmake .. [-G <your preferred toolset>]

CMake will create project files for a given toolset.  What toolset you use depends on your platform, and there's usually a default.  On a Windows machine, it defaults to Visual Studio, although if you have more than one version installed it may require you to specify which one you want.  You can specify a specific platform using -G.  

    cmake -h

Will show you a list of supported generators on your platform.

## Building

Depends on your build tool.  If you're using Visual Studio or XCode you can just say 'File, Open Project' or something to that effect and point it at the OculusRiftInAction/build directory.  

# Supported platforms

## On Windows 8 with Visual Studio 2013 Desktop Edition

The following generators have all been found to work

Suitable generators

* "Visual Studio 12" 
* "Visual Studio 12 Win64" 

Note that "Visual Studio 12" actually corresponds to Visual Studio 2013.  

It's worthwhile to note that CMake may not show the Win64 options in the list of generators, even if they're supported.
Win64 refers to the creation of projects that produce 64 bit binaries, NOT the version of Visual Studio itself. 

The libraries needed to build the core examples are included and built as part of the project, but some examples will 
only be built if additional libraries are present, such as OpenCV.  If you want to build these, it's important to make 
sure you match up the 32/64 bit nature of the project you create with the installed version of OpenCV, etc.  

## On OSX with XCode

* "Xcode"

## On Ubuntu using Eclipse

Suitable generators

* "Eclipse CDT4 - Unix Makefiles"
* "Eclipse CDT4 - Ninja"
* "Unix Makefiles"
* "Ninja"

Note that the CMake Eclipse generators will complain about a build directory that is a child of the source directory, 
but I have not experienced any issues with this. 

I highly recommend using the Ninja builder instead of makefiles.  It's dramatically faster.  Note that the Ubuntu package for the ninja builder is `ninja-build` *not* `ninja`, which is an unrelated tool.  

