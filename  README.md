=== fhemaosp Build Instructions ===

# Latest AOSP Update

# Android 5.1.1_r3 = LMY48B

# Get fhemaosp Source

$ mkdir ~/fhemaosp
$ cd ~/fhemaosp
$ repo init -u https://github.com/fhemaosp/platform_manifest -b master
$ repo sync


# Building

$ cd ~/noobbuilds
$ make clobber
$ source build/envsetup.sh
$ lunch aosp_shamu-userdebug 
$ export USE_CCACHE=1           (only if ccache is setup!!!!)
$ make -j `getconf _NPROCESSORS_ONLN` otapackage 
  
# Update Source

$ cd ~/noobbuilds
$ repo sync

# Cleaning

$ cd ~/noobbuilds
$ make clobber
