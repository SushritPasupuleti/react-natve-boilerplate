# React Native Setup

```bash
npx react-native init AwesomeProject
```
## iOS Specific

```
brew install cocoapods
sudo gem install ffi
brew install watchman
sudo xcode-select --switch /Applications/Xcode.app

cd ./ios
pod install
```

Run

```bash
npx react-native run-android
```

Good to haves

```bash
npm i redux react-redux redux-thunk axios @react-navigation/native @react-navigation/stack react-native-gesture-handler react-native-reanimated react-native-screens react-native-safe-area-context @react-native-community/masked-view react-native-vector-icons
react-native link react-native-vector-icons react-native-paper
```

Getting Signing Certificate:

```bash
keytool -list -v -alias androiddebugkey -keystore %USERPROFILE%\.android\debug.keystore
```

## Icons setup

```bash
cd android && ./gradlew clean
```

Add the following to `./rnproject/android/app/build.gradle`

```gradle
apply from: file("../../node_modules/@react-native-community/cli-platform-android/native_modules.gradle"); applyNativeModulesAppBuildGradle(project)
project.ext.vectoricons = [
    iconFontNames: ['MaterialCommunityIcons'] // Name of the font files you want to copy
]

apply from: "../../node_modules/react-native-vector-icons/fonts.gradle"
```

Option: Manually

- Copy the contents in the Fonts folder to `android/app/src/main/assets/fonts` (note lowercase fonts folder).