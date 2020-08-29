This folder only contains compiled code and assets. Please do not modify files in this folder, the app code is in the "src" folder.

The config.json values are ignored by the app. This file is informative for Continous Integration processes used by Moodle HQ.



debug keystore generate
```
keytool -genkey -v -keystore debug.keystore -storepass android -alias androiddebugkey -keypass android -keyalg RSA -keysize 2048 -validity 10000
```

Release key

```
 keytool -genkey -v -keystore bienguru-release.keystore -alias bienguru -keyalg RSA -keysize 2048 -validity 10000
 ```