# android_device_xiaomi_cepheus
For building TWRP for Xiaomi Mi 9

TWRP device tree for Xiaomi Mi 9

## Features

TO DO: 

-ADB
-Encryption
-UI

## Compile

First checkout minimal twrp tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-12.1
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/cepheus" name="JoK3rLeE/twrp_device_xiaomi_cepheus" remote="github" revision="android-12.1" />
```

Finally execute these:

```
. build/envsetup.sh
lunch twrp_cepheus-eng
mka recoveryimage
```

To test it:

```
fastboot boot out/target/product/cepheus/recovery.img
```

## Thanks

- Thanks to @PeterCxy for the commits and the base: https://github.com/PeterCxy/android_device_xiaomi_violet-twrp
- Thanks to @mauronofrio for initial cepheus twrp tree: https://github.com/mauronofrio/android_device_xiaomi_cepheus
- Thanks to @Pranav-Talmale for android 12.1 raphael trees base: https://github.com/Pranav-Talmale/android_device_xiaomi_raphael-twrp
