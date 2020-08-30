Moodle Mobile
=================

This is the primary repository of source code for the official Moodle Mobile app.

* [User documentation](http://docs.moodle.org/en/Moodle_Mobile)
* [Developer documentation](http://docs.moodle.org/dev/Moodle_Mobile)
* [Development environment setup](http://docs.moodle.org/dev/Setting_up_your_development_environment_for_Moodle_Mobile_2)
* [Bug Tracker](https://tracker.moodle.org/browse/MOBILE)
* [Release Notes](http://docs.moodle.org/dev/Moodle_Mobile_Release_Notes)

License
-------

[Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0)

Big Thanks
-----------

Cross-browser Testing Platform and Open Source <3 Provided by [Sauce Labs](https://saucelabs.com)

![Sauce Labs Logo](https://user-images.githubusercontent.com/557037/43443976-d88d5a78-94a2-11e8-8915-9f06521423dd.png)

Path Varibales

```
export CORDOVA_ANDROID_GRADLE_DISTRIBUTION_URL=https\://services.gradle.org/distributions/gradle-4.10.1-all.zip
export ANDROID_SDK_ROOT=/Users/ajandersingh/Library/Android/sd
export ANDROID_HOME="/Users/ajandersingh/Library/Android/sdk"
export PATH="$PATH:$ANDROID_HOME/tools"
export PATH="$PATH:$ANDROID_HOME/build-tools"

export PATH="$PATH:$ANDROID_HOME/platform-tools"

# avdmanager, sdkmanager
export PATH=$PATH:"/Users/ajandersingh/Library/Android/sdk/tools/bin"

# adb, logcat
export PATH=$PATH:"/Users/ajandersingh/Library/Android/sdk/platform-tools"

# emulator
export PATH=$PATH:"/Users/ajandersingh/Library/Android/sdk/emulator"
```

cordova plugin save
ionic cordova platform rm ios
ionic cordova platform add ios
