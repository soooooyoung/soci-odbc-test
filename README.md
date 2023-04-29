# SOCI Sample Project
Sample implementation of SOCI for MS SQL Server Connection using ODBC Driver

# Prerequisites 
- MS SQL Server 
- C++ compiler
- CMake 2.8+
- ODBC Driver 
- (optional) Boost C++ Libraries (DateTime, Fusion, Optional, Preprocessor, Tuple)

# Getting Started 

Download appropriate version of SOCI for your needs from [official source](https://sourceforge.net/projects/soci/).

Extract the downloaded zip file and create build directory.
```
mkdir build
cd build
```
### Create Files using CMake

Here are some options you may want to consider before creating build files.

#### Enable ODBC
This is required if you want to use SOCI with ODBC for MS SQL Server Connection.
```
-DWITH_ODBC=ON
```
You also need to locate include and library directories for ODBC
```
-DODBC_INCLUDE_DIR="C:/Program Files (x86)/Windows Kits/10/Include/10.0.22000.0/um" 
-DODBC_LIBRARIES="C:/Program Files (x86)/Windows Kits/10/Lib/10.0.22000.0/um/x64/odbc32.lib"
```
#### Enable Boost
If you want to use SOCI with support for Boost, enable following option. Include root directory of your local Boost.
```
-DWITH_BOOST=ON -DBOOST_ROOT="C:/local/boost"
```
#### Specify SOCI Installation Path
You can specify location of SOCI by adding following option
```
 -DCMAKE_INSTALL_PREFIX=<Preferred Location>"
```
### Build Project
Here is an example of complete CMake command.
```
cmake -G "Visual Studio 17 2022" -A x64 -DWITH_BOOST=ON -DBOOST_ROOT="C:/local/boost" 
-DWITH_ODBC=ON -DODBC_INCLUDE_DIR="C:/Program Files (x86)/Windows Kits/10/Include/10.0.22000.0/um" 
-DODBC_LIBRARIES="C:/Program Files (x86)/Windows Kits/10/Lib/10.0.22000.0/um/x64/odbc32.lib" ..
```
After executing the completed command, build project ALL_BUILD and INSTALL and SOCI will be installed. Make sure to add SOCI to your project by adding additional include directories and library directories.


