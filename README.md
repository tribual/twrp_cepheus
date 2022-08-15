# Device tree for Mi 9 (codenamed _"cepheus"_)

### Device specifications

| Device                  | Xiaomi Mi 9                                                   |
| ----------------------: | :------------------------------------------------------------ |
| SoC                     | Qualcomm SDM855 Snapdragon 855                                |
| CPU                     | 1x2.84 GHz Kryo 485 + 3x2.4 GHz Kryo 485 + 4x1.8 GHz Kryo 485 |
| GPU                     | Adreno 640                                                    |
| Memory                  | 6GB / 8GB RAM (LPDDR4X)                                       |
| Shipped Android version | 9.0                                                           |
| Storage                 | 64GB / 128GB / 256GB UFS 2.1 flash storage                    |
| Battery                 | Non-removable Li-Po 3300 mAh                                  |

### Features 
**Works**

- Booting.
- **Decryption** (Android 12)
- ADB
- MTP
- OTG
- Vibration

### Compile

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
lunch twrp_cepheus-eng && mka recoveryimage
```

To test it:

```
fastboot boot out/target/product/cepheus/recovery.img
```

## Thanks

- Thanks to @PeterCxy for the commits and the base: https://github.com/PeterCxy/android_device_xiaomi_violet-twrp
- Thanks to @mauronofrio for initial cepheus twrp tree: https://github.com/mauronofrio/android_device_xiaomi_cepheus
- Thanks to @Pranav-Talmale for android 12.1 raphael trees base: https://github.com/Pranav-Talmale/android_device_xiaomi_raphael-twrp
