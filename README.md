# openjfx-build
How to build OpenJFX

# OpenJFX 10 on Windows

## Prerequisit

* Windows 64bit because Java9+ is only available for 64bit operating systems
* Install Tortoise Hg - https://tortoisehg.bitbucket.io/download/index.html

## Prepare

* Create a directory C:/Dev/openjfx/10-dev
* Clone http://hg.openjdk.java.net/openjfx/10-dev/rt/ into the above directory

## Software to install

Download the following components
* JDK 9 SDK - http://www.oracle.com/technetwork/java/javase/downloads/index.html
* Gradle 4.3.1 - https://services.gradle.org/distributions/gradle-4.3.1-bin.zip
* DirectX SDK - https://www.microsoft.com/en-us/download/details.aspx?id=6812
* VS Studio 2017 Community Edition - https://www.visualstudio.com/de/downloads/
* Cygwin 64bit - https://cygwin.com/install.html

Install:
* DirectX SDK
* VS Studio 2017
* Cygwin 64bit

Unzip:
* Gradle to C:/Dev/openjfx/gradle-4.3.1

Remember the following informations:
* Install location of "VS Studio"-Build directory for VS 2017 it is eg `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build`
* Install location of MSVC currently `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Tools\MSVC\14.11.25503` - the last segment of this path is changing
* Install location of JDK9 eg `C:\Program Files\Java\jdk-9.0.1`

## Running a build
Open cygwin shell and run

```bash
# setup some vars (see above)
export VS150COMNTOOLS="C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build"
export JAVA_HOME="C:\Program Files\Java\jdk-9.0.1"
export MSVC_VER=14.11.25503

# navigate to the checked out sources
cd /cygdrive/c/Dev/openjfx/10-dev/

# clean up from previous builds
rm -rf build

# build sdk
/cygdrive/c/Dev/openjfx/gradle-4.3.1/bin/gradle sdk
```
