
=== fhemaosp Build Instructions ===

# Latest AOSP Update

N6 = Nexus 6 =   shamu  = Android 5.1.1_r5

# Get fhemaosp Source

	$ mkdir ~/fhemaosp
	$ cd ~/fhemaosp
	$ repo init -u https://github.com/fhemaosp/platform_manifest -b master
	$ repo sync
	
# Build It

	$ cd ~/fhemaosp
	$ source build/envsetup.sh
	$ make clobber
	$ lunch aosp_shamu-userdebug
	$ export USE_CCACHE=1   !!!!!!!!! only use this line if you have CCACHE setup.!!!!!!!!!!!!
	$ make -j `getconf _NPROCESSORS_ONLN` otapackage
