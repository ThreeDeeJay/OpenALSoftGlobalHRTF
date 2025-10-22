# OpenAL Soft global HRTF
Adds OpenAL Soft HRTF files and configuration to enable 3D audio for headphones in all apps/games using OpenAL Soft, even if the library was compiled without the built-in HRTF.

## How to use

### Requirements
- Android device rooted with [Magisk](https://topjohnwu.github.io/Magisk/install.html).
- App/game using (preferably recent) OpenAL Soft library. You can use a [root-capable file manager](https://mixplorer.com/beta/) to [search `/data/app/` for `openal`](https://github.com/user-attachments/assets/8cefe250-ab91-4d9d-8dfd-ab9df92a816d). If it uses generic OpenAL or old OpenAL Soft and your device is rooted, you can replace the library (usually named `libopenal.so` in the app's `data/app/RANDOMSTRING/PACKAGENAME/lib/...`) with OpenAL Soft [armeabi-v7a (32-bit)](https://nightly.link/kcat/openal-soft/workflows/ci/master/soft_oal-Android_armeabi-v7a-Release.zip) or [arm64-v8a (64-bit)](https://nightly.link/kcat/openal-soft/workflows/ci/master/soft_oal-Android_arm64-v8a-Release.zip).

### Installation
- Download module Zip file
- (Optional) use your own/matching HRTF:
  - Extract the Zip file.
  - Find the HRTF that sounds most positionally accurate to you using [this blind test](https://kutt.it/FindMyHRTF) or the [MHR database](https://kutt.it/FindOpenALSoftHRTF) and download the MHR file.
  - Replace the HRTF in `/system/etc/xdg/openal/hrtf/HRTF.mhr` (you can use any filename but just keep the file you want to use).
  - Compress `module.prop` and `system` back into a Zip file.
- Flash the module in Magisk and reboot.

The app/game should now use your HRTF and you'll enjoy full 3D spatial audio (if supported, otherwise it'll just virtualize surround/stereo), and the [log](https://play.google.com/store/apps/details?id=com.conena.logcat.reader) should look like this:
<img src="https://github.com/user-attachments/assets/288bb8ae-e98f-4152-bcc2-1ef2290ec4bd" />

### Compatibility
Android games/apps that support OpenAL Soft will be added to the [Binaural Audio Database](https://airtable.com/appayGNkn3nSuXkaz/shrZP6E5xqQjsvplj?SEv24=b%3AWzAsWyJ1YTJPdCIsNixbInNlbDBzb0xqREpMSGZiWDdPIl0sIjJZUTBPIl0sWyI2NFJaeiIsNixbInNlbFhwQ0NYaEFtNHQ1cDAyIl0sImcwWWJHIl1d&eCzZW=recbLzCCaygURm8bh).

## Credits

> * SADIE Database Copyright 2018 The University of York
This product includes data developed at The Audio Lab, University of York, UK (Cal Armstrong, Lewis Thresh, Gavin Kearney) as part of the [SADIE Project](https://www.york.ac.uk/sadie-project/database.html). 
