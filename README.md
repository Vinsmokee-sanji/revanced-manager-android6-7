# ReVanced Manager builds for Android 6.0-7.1

Custom builds of ReVanced Manager, for Android 6.0-7.1

Combining with my [ReVanced Patches for YouTube 17.34.36](https://github.com/kitadai31/revanced-patches-android6-7), you can build YouTube ReVanced easily with an Android 6 or 7 device alone.

## Download
Go to [Releases](https://github.com/kitadai31/revanced-manager-android6-7/releases) page

## Announcement (2023/04/16)
### It may not work on Android6.0!

Apparently it doesn't work on Android 6.0.  
It is reported that this error was shown and Manager was aborted.

```
brut.androlib.AndrolibException:brut.common.brutException: could not exec (exit code = 1): [/data/app/app.revanced.manager.flutter-1/lib/arm64/libaapt2.so, ...
```

I'm sorry for releasing this app without sufficient confirmation of its operation.

Unfortunately, I do not have Android 6.0 devices, so I cannot confirm that it works.  
The emulator was not helpful as it displayed a mysterious error.

If anyone has successfully patched on Android 6.0, please report it on the Discussions page or my twitter!

## What I did to support Android 6 & 7
- Change minSdkVersion to 23
- Fix dependent library problem
- Change apksig library to another one
  - Thank you [MuntashirAkon/apksig-android](https://github.com/MuntashirAkon/apksig-android) !
- Enable java.nio API desugaring library
- Remove unsupported java.nio.file API from patches ([Patches side change](https://github.com/kitadai31/revanced-patches-android6-7/commit/aada74d77793c9783a7015a051474a1f6567eb60))

## Prerequisites
1. Android 6.0 or higher
2. Does not work on some armv7 (32bit) devices
3. Vanced MicroG (https://github.com/inotia00/VancedMicroG/releases) is required for YouTube and YouTube Music (Only for non-root)

# How to patch
The usage is same as the original ReVanced Manager. This section describes the points specific to Android 6-7.

## YouTube
Official patches and latest Extended patches are not compatible with YouTube 17.34.36. (17.34.36 is the final version for Android 6 & 7.)

Therefore, I recommend changing the patch source to [kitadai31/revanced-patches-android6-7/](https://github.com/kitadai31/revanced-patches-android6-7), provided by me.

<img src="https://user-images.githubusercontent.com/90122968/230283820-dd55a454-6267-43dc-a6c0-eb1b6f5f4e15.png" width="240">

See [How to build](https://github.com/kitadai31/revanced-patches-android6-7/wiki/How-to-build) page in kitadai31/revanced-patches-android6-7.

## YouTube Music
**ReVanced Music** - No plobrem with recommended patches.

**ReVanced Extended Music** - The following patches are not available.

- `Custom Branding xxx`
- `Optimize Resource`
- `Translations`

These patches cause `NoSuchMethodError` so you have to exclude these patches.

> **Note**  
> Instead of this ReVanced Manager, you can also use [RVX Builder](https://github.com/inotia00/rvx-builder) or [Revancify](https://github.com/decipher3114/Revancify) or [ReVanced CLI](https://github.com/revanced/revanced-cli) on your old device.  
These solutions will allow you to apply all patches to YT Music.

## Other apps
You can patch as usual as original Manager.

Please note that errors may occur, such as "NoSuchMethodError", "NoClassDefFoundError".  
If an error occurred and the error was specific to Android 6 & 7 , please give up.

However, you can use ReVanced Builder or ReVanced CLI instead of this ReVanced Manager.  
Also, if you have other Android 8+ devices (or PC), you may want to use ReVanced Manager on that device and transfer patched APK to your old devices.
