# SHRP_device_xiaomi_vela
For building TWRP for Xiaomi Mi CC 9 Meitu Edition

TWRP device tree for Xiaomi Mi CC 9 Meitu Edition
## Features

Works:

- ADB
- Decryption of /data
- Screen brightness settings
- Correct screenshot color
- MTP
- Flashing (opengapps, roms, images and so on)
- Backup/Restore (Needs more testing)
- USB OTG

TO-DO:

- Vibration support

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u https://github.com/liangsheng8708/SHRP_device_xiaomi_vela.git -b master
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/vela" name="liangsheng8708/SHRP_device_xiaomi_vela" remote="github" revision="master" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_vela-eng
mka recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot boot out/target/product/vela/recovery.img
```

## Other Sources

Using precompiled stock kernel.

## Thanks

- Thanks to @PeterCxy for the commits and the base: https://github.com/PeterCxy/android_device_xiaomi_violet-twrp
