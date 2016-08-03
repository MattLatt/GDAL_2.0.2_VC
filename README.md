# GDAL_2.0.x_VC
This repository contain Visual C++ 2010 workspace of the GDAL 2.0.x library (http://gdal.org)

    * The Folder gdal-2.0.3 contain the gdal 2.0.3 source release (http://download.osgeo.org/gdal/2.0.3/gdal203.zip).
	The file ./gdal-2.0.3/port/cpl_config.h.vc has been renamed to ./gdal-2.0.3/port/cpl_config.h in order to
	compile with MS visual C++ and the file ./gdal-2.0.3/gcore/Version.rc has been slightly modified (included 
	gdal_version.h instead of gdal.h) to avoid the RC1015 error compilation I have with VS 2010. I kept a copy of
	the original file provided by OSgeo (./gdal-2.0.3/gcore/Version.rc.orig).

	* The folder libgdal-2.0.3 contain a MS Visual Studio Solution with all the workspaces and a "binaries"
	sub-folder with each architecture and configuration binaries copied by VC post-build steps.
	There is both dynamic (dll) and static workspaces (lib) of GDAL 2.0.3 with 4 test workspaces:
	
		+ test_dynamic_gdalbuildvrt workspace:
		this is the gdalbuildvrt code provided by gdal (in the app folder of the source package) in a 
		"windows console" workspace dynamically linked to GDAL 2.0.3
		
		+ test_dynamic_ogr2ogr workspace:
		this is the ogr2ogr code provided by gdal (in the app folder of the source package) in a 
		"windows console" workspace dynamically linked to GDAL 2.0.3
			
		+ test_static_libgdal-2.0.3 workspace:
		this is a simple console program that dump all the supported drivers (GDAL/OGR) with theire 
		capabilities (i.e. Read/Write)
		
		+ test_static_gdalinfo workspace:
		this is the gdalinfo code provided by gdal (in the app folder of the source package) in a 
		"windows console" workspace statically linked to GDAL 2.0.3
	
	* The 3rdpart folder contain the library not provided internally by GDAL and necessary for some format I choosed to add (OSM,...).
	For now it contain the libexpat (linlked dynamically) and libsqlite3.12 amalgamation included in the GDAL workspaces.


/!\ Due to GitHub (free version) limitation I've deleted the static version of gdal-2.0.3.lib (more than 650 MB),
so you will have to rebuild the static lib version.
## 2016-08-03:

	- Compiled with the HDF5 drivers (dynamically linked to the v1.8.17 of the HDF5 lib, binaries provided in the 3rdpart folder) 

## 2016-07-21: 	

	- Compiled with the july release of gdal 2.0.3
	
	- Compiled with lib geos 3.5.0 linked dynamically (MS VC Workspace provided in the 3rdpart folder)
	
	- Corrected the test_static_libgdal-2.0.3 main.cpp file (removed OGRRegisterAll as it's already called by GDALRegisterAll)
	
	- Renamed the repository GDAL_2.0.x_VC
		
	- Compiled with the following gdal drivers: ARG, WMS, and MBTILES
	
	- Compiled with the following ogr drivers: VFK, WFS, SQLITE, CSW, XLSX, GFT

	- Compiled with the libcurl 7.49.1, provided in the 3rdpart folder. I used the libcurl compiled
	for windows by Stefan Kanthak (home.arcor.de/skanthak/curl.html)

    - Compiled with the ECW and JP2ECW driver support (in Read Only mode), ECW 4.3 RO SDK provided in the 3rdpart folder.
	The SDK is provided as downloaded except I've renamed all the "win32" folders to "x86".
	
	- Compiled with the ERS driver support.
	
	- Corrected bad Preprocessor value in the Release (in Dynamic and static workspace for both architectures).	
	
What still need to be done :
	
	- add iconv library
	   
    - test if it's possible to use Unicode charset (instead of Multi-Byte)
	
	
## 2016-07-04: 

    - Added lib proj (4.9.2) dll workspace for both architecture in the 3rdpart folder
	
	- Added a new test project "test_dynamic_ogr2ogr"

What still need to be done :

    - add ECW driver

	- add V2.0.3 new drivers
   
    - test if it's possible to use Unicode charset (instead of Multi-Byte)

## 2016-06-29:

    - Added x64 version of all the workspaces (dll, lib and tests).
	I've compiled the 3rd part library libexpat for x64 architecture excluding in UNICODE mode for now

	
## 2016-06-28: 
What is compiling :

    - x86 version of all the workspaces (dll, lib and tests) 


