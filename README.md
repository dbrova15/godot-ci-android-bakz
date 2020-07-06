# godot-ci-android-bakz

## What is this?

Docker image and gitlab pipelines configuration for exporting your Godot project to Android. Supports debug and release exports.

## How it works?

Docker image installs Godot and all necessary dependencies for Android debug export (templates, SDKs, debug keystore etc.). Then it sets up Godot editor settings for android debug export. Release export is also supported, but you need to generate release keystore.

## How can I use it in my project?

Copy .gitlab-ci.yml to your project repository.  
Commit your project's export_presets.cfg to the repository. Presets should be configured with exports that match the names used in .gitlab-ci.yml:
- "Android" (for debug export)
- "Android Release Armeabi-v7a"
- "Android Release Arm64-v8a"
- "Android Release x86"
- "Android Release x86-64"  

You can follow offical tutorial and skip the initial setup.  

### Important:
Make sure to read .gitlab-ci.yml. It has comments how to setup release export properly and unit tests.

## Customization
Naturally you can customize this configuration, for exmaple by skipping some target HW. Simply comment or remove unnecessary things. Adding other targets (for example Windows) should be easily found on the web - google it.

## The basis
As a basis, I took the repository https://github.com/myood/godot-ci-android-export
