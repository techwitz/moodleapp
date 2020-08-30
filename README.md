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
# zipalgin
export PATH=$PATH:"/Users/ajandersingh/Library/Android/sdk/build-tools/30.0.2"
```

cordova plugin save
ionic cordova platform rm ios
ionic cordova platform add ios
sudo npm install -g ios-deploy --unsafe-perm=true
sudo npm install -g cordova-res --unsafe-perm=true

debug keystore generate
```
keytool -genkey -v -keystore debug.keystore -storepass android -alias androiddebugkey -keypass android -keyalg RSA -keysize 2048 -validity 10000
```

#Generating a release build of an app
To generate a release build for Android, run the following cli command:

```
ionic cordova build android --prod --release
```

#Signing an APK
First, the unsigned APK must be signed. If a signing key has already been generated, skip these steps and use that one instead. Generate a private key using the keytool command that comes with the Android SDK:

```
 keytool -genkey -v -keystore bienguru-release-key.keystore -alias bienguru -keyalg RSA -keysize 2048 -validity 10000
 keytool -importkeystore -srckeystore bienguru-release-key.keystore -destkeystore bienguru-release-key-pkcs12.keystore -deststoretype pkcs12

 password: pa55w0rd
 ```

To sign the unsigned APK, run the jarsigner tool which is also included in the Android SDK:
```
ionic cordova run android --aot --release
jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore bienguru-release-key.keystore platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk release

password: pa55w0rd
```

Finally, the zip align tool must be ran to optimize the APK. The zipalign tool can be found in ```/path/to/Android/sdk/build-tools/VERSION/zipalign```. For example, on macOS with Android Studio installed, ```zipalign``` is in ```~/Library/Android/sdk/build-tools/VERSION/zipalign```

```
zipalign -v 4 platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk bienguru-released.apk
```


 ##Always make chengs in  src/config.json file