# BlueBook Instructions

After cloning this repo, install the dependencies:

`cd ProjectName`

`yarn install`

Link all native dependencies

`react-native link`

Install the Podfile:

`cd ios`

`pod install`

## Installing all dependencies in for development

Please follow this guide and install the correct dependencies for your current OS and the OS that you want to build (iOS or Android)

https://facebook.github.io/react-native/docs/getting-started.html#installing-dependencies

## Setup

### Google config

There is two files that you need to edit to make work the push notifications, google sign up and other Google Services:

1. `ios/GoogleService-Info.plist`
2. `android/app/google-services.json`

You need to create a project in firebase console and update all the credentials on both files (current files have invalid credentials)

Also, you will need to modify your URL types in `Info`, follow [this](https://github.com/react-native-community/react-native-google-signin/blob/master/docs/ios-guide.md#3-xcode-configuration) instructions:

Finally, you will need to add `GoogleService-Info.plist` (file reference) to your iOS project via xcode.

1. Open `bluebook.xcodeproj`in xcode.
2. Go to main target > Build Phases > Copy Bundle resources
3. Tap un add button
4. Search the `GoogleService-Info.plist`inside `ios` folder.
5. Make sure you can see `GoogleService-Info.plist` inside in xcode.

## Running with React Native CLI

### Running Android simulator

1. Activate android emulator following this [instructions](https://facebook.github.io/react-native/docs/running-on-device)
2. `react-native run-android` from project home folder

### Running iOS simulator

1. Go to `ios` folder and run `pod install`
2. Run `react-native run-ios` from project home folder.

If you find any compiling problems, try to clean your cache.

## TroubleShooting

### Module "redux" does not exist in the haste module map.

Run the following:

`watchman watch-del-all`
`rm -rf node_modules && npm install`
`rm -rf /tmp/metro-bundler-cache-*` or `npm start -- --reset-cache`
`rm -rf /tmp/haste-map-react-native-packager-*`
