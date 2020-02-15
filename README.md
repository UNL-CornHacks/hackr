# Initiated with create-react-native-web-app


## Dependencies

### Web
- Node
- yarn

### Android
- Android Studio 
- (Windows) Intel x86 Emulator Accellerator (HAXM Installer) - this can be found in Android Studio -> Settings -> Apprearance & Behavior -> System Settings -> Android SDK -> SDK Tools
- Android SDK
- Android SDK tools (possibly)

### iOS
- IDK yet

## Installation

- Android - Install [adb (Android Debug Bridge)](https://developer.android.com/studio/releases/platform-tools.html)
- IOS - Xcode and an apple device required


### Launch Server/local web
$ yarn web

### Run in another terminal
#### IOS (simulator)
$ yarn ios

#### Android (connected device or android studio)
$ yarn android


## Debugging

Open dev menu:
1. CMD+D (IOS) / CMD+M (Android)
2. Press "Enable Live-Reload"

[React native docs - debugging real devices guide](http://facebook.github.io/react-native/releases/0.49/docs/running-on-device.html)

[React native docs - debugging guide](http://facebook.github.io/react-native/docs/debugging.html)

[Network calls in the devtools](http://www.preslav.me/2017/03/26/debugging-network-calls-in-react-native-using-the-chrome-debugger/)
 ./android/app/build/outputs/apk

[React native docs - Android signed apk](http://facebook.github.io/react-native/releases/0.49/docs/signed-apk-android.html)

[React native docs for IOS](http://facebook.github.io/react-native/releases/0.49/docs/running-on-device.html#building-your-app-for-production)


## Troubleshooting
Issues with Xcode 10 (newest version) - https://github.com/facebook/react-native/issues/19573

If you got `Execution failed for task ':app:compileDebugAidl'` when running `yarn android`, try to update Android Gradle plugin to version 3.1.1 and Gradle to version 4.4.

Here is how to do that:
1. Open **Android Studio**
1. Open the `android` project
<br /><img src="https://cdn-images-1.medium.com/max/800/1*jyLo3Jk-nudieT3aaEzUBQ.png" />
1. Click `Update` on this prompt
<br /><img src="https://cdn-images-1.medium.com/max/800/1*7I2tqGZ9C63aUGOtae-XHg.png">
1. Wait for Android Studio syncing the project.

If you got `FAILURE: Build failed with an exception.`, examine the warnings:

1. WARNING: `The specified Android SDK Build Tools version (23.0.1) is ignored, as it is below the minimum supported version (27.0.3) for Android Gradle Plugin 3.1.1.`
<br />Solution: Update Build Tools
<br /><img src="https://cdn-images-1.medium.com/max/1000/1*GUlICoUm4cU4KzUfps3W0Q.png" />

1. WARNING: `Configuration 'compile' is obsolete and has been replaced with 'implementation' and 'api'.`
<br />Solution: Change `compile` to `implementation` by open `app/build.gradle` file, change `dependencies` section (line 139) to use `implementation` instead of `compile` .

```java
dependencies {
  implementation fileTree(dir: "libs", include: ["*.jar"])
  implementation "com.android.support:appcompat-v7:23.0.1"
  implementation "com.facebook.react:react-native:+"
}
```

Sync it again and now you can close Android Studio. See issue [#7](https://github.com/VISI-ONE/create-react-native-web-app/issues/7#issuecomment-432263368) for your references.


## Resources
- [React Native for Web (react-native-web)](https://github.com/necolas/react-native-web)
- [React](https://reactjs.org/)
- [React Native](http://facebook.github.io/react-native/)
- [Create React App](https://github.com/facebook/create-react-app)
- [Create React Native App](https://github.com/react-community/create-react-native-app)
