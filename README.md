# ReVanced Manager builds for Android 6.0-7.1

Custom builds of ReVanced Manager, for Android 6.0-7.1

Combination with my [ReVanced Patches for YouTube 17.34.36](https://github.com/kitadai31/revanced-patches-android6-7), you can build YouTube ReVanced easily with an Android 6 or 7 device alone.

## Download
Go to [Releases](https://github.com/kitadai31/revanced-manager-android6-7/releases) page

## What I did to support Android 6 & 7
- Change minSdkVersion to 23
- Fix Device Apps plugin library problem
- Change apksig library to another one
  - Thank you [MuntashirAkon/apksig-android](https://github.com/MuntashirAkon/apksig-android) !
- Enable Java nio API desugaring library
- Remove unsupported java.nio.file API from patches (Patches side change)

## Prerequisites
1. Android 6.0 or higher
2. Does not work on some armv7 (32bit) devices
3. [Vanced MicroG](https://github.com/inotia00/VancedMicroG/releases) is required for YouTube and YouTube Music (Only for non-root)

# How to patch

## YouTube
Official patches and Extended patches are not compatible with YouTube 17.34.36. (Android 6 & 7 final version)

Therefore, I recommend changing the patch source to [kitadai31/revanced-patches-android6-7](https://github.com/kitadai31/revanced-patches-android6-7), that I'm providing.

<img src="https://user-images.githubusercontent.com/90122968/230283820-dd55a454-6267-43dc-a6c0-eb1b6f5f4e15.png" width="240">

## YouTube Music
ReVanced Music - No plobrem with recommended patches.

ReVanced Extended Music - The following patches are not available.

- `Custom Branding xxx`
- `Optimize Resource`
- `Translations`

These patches cause NoSuchMethodError. You have to exclude these patches.

## Other apps
You can patch as usual as original Manager.

Please note that errors may occur, such as NoSuchMethodError, NoClassDefFoundError.  

If an error occurred and the error was specific to Android 6 & 7 , please give up.

However, you can use ReVanced CLI, ReVanced Builder (or rvx-builder) or Revancify instead of this ReVanced Manager.

Also, if you have other Android 8 or higher devices, you can use ReVanced Manager on that device and transfer patched APK to your old devices.
