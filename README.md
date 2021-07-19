# JSC Android Builder

## Requirements

* Homebrew (https://brew.sh/)
* GNU coreutils `brew install coreutils`
* Node `brew install node`
* Java 8: `brew tap caskroom/versions && brew cask install java8`
* Android SDK: `brew cask install android-sdk`
  * Run `sdkmanager --list` and install all platforms, tools, buildtool v28.0.3, cmake (>=3.10)
  * Set `$ANDROID_HOME` to the correct path (in ~/.bashrc or similar)
  * Set `export PATH=$PATH:$ANDROID_HOME/platform-tools:$ANDROID_HOME/tools/bin`
* Android NDK r19c: download from [NDK Archives](https://developer.android.com/ndk/downloads/older_releases.html)
  * Set `export ANDROID_NDK=/path/to/android-ndk` (>=19)
* Make sure you have Ruby (>2.3), Python (>2.7), Git, SVN, gperf

## Build instructions

1. Clone this repo
2. `npm run clean` will clean everything (artifacts, downloaded sources)
3. Update the version in package.json. The version will be printed by JSC lib as soon as it loads
3. Update the config section under `package.json` to the desired build configuration
4. Update patches if needed (don't forget to update the `printVersion` patch in jsc.patch)
5. `npm run download`: downloads all needed sources
6. `npm run start`: builds jsc (this might take some time...)

* The android-jsc AAR will be available at `/dist`
* The android-jsc AAR (so without strip) will be available at `/dist.unstripped`
