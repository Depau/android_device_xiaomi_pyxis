# android_device_xiaomi_pyxis
For building TWRP for Xiaomi Mi 9 Lite / Mi CC9

TWRP device tree for Xiaomi Mi 9 Lite / Mi CC9


## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-9.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/pyxis" name="Depau/android_device_xiaomi_pyxis" remote="github" revision="android-9.0" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_pyxis-eng
mka recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot boot out/target/product/pyxis/recovery.img
```
