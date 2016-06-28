# GDAL_2.0.2_VC
This repository contain Visual C++ 2010 workspace for th lib GDAL 2.0.2 (http://gdal.org)

There is both dynamic (dll) and static workspaces (lib) of GDAL 2.0.2 with 3 test workspaces:

    * test_dynamic_gdalbuildvrt workspace:
    this is the gdalbuildvrt code provided by gdal (in the app folder of the source package) in a "windows console" workspace
    dynamically linked to GDAL 2.0.2
    
    * test_static_libgdal-2.0.2 workspace:
    this is a simple console program that dump all the supported drivers (GDAL/OGR) with theire capabilities (i.e. Read/Write)
    
    * test_static_gdalinfo workspace:
    this is the gdalinfo code provided by gdal (in the app folder of the source package) in a "windows console" workspace
    statically linked to GDAL 2.0.2

Libexpat 2.10 and libsqlite 3.12 are provided in the "3rdpart" folder

## 2016-06-28: Warning this is a work in progress
What have been tested:

    - x86 version of all the workspaces (dll, lib and tests) 

What need to be done :

    - adding Proj.4 lib
    
    - adding ECW driver
    
    - building libexpat for x64 architecture to test x64 version of all the workspaces
    
    - test if it's possible to use Unicode charset (instead of Multi-Byte)
    
