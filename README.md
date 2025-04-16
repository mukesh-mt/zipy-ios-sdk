<p align="center">
  <a href="https://www.zipy.ai/" target="_blank" align="center">
    <img src="https://cdn.prod.website-files.com/60d19df3e49f1bce12e33927/64ddac8c19511387004a5020_Zipy%20Logo%20Vector%20(1).svg" width="280">
  </a>
  <br />
</p>

Zipy SDK for iOS
===========

## ZipyiOS SDK Guide

This guide explains how to implement and use the main features of the ZipyiOS SDK in your iOS application.

## Table of Contents
- [Installation](#installation)
- [Initialization](https://docs.zipy.ai/ios-setup/install-in-an-ios-app)
- [User Identification](https://docs.zipy.ai/ios-setup/identify-users)
- [Logging](https://docs.zipy.ai/ios-setup/custom-logging)
- [Session URL](https://docs.zipy.ai/ios-setup/session-url-retrieval)
- [Session Control](https://docs.zipy.ai/ios-setup/session-recording-control)
- [UI Custom Masking](https://docs.zipy.ai/ios-setup/input-masking-and-custom-masking)
- [Screen Tracking & Tagging](https://docs.zipy.ai/ios-setup/screen-tracking-and-tagging)

## Installation

### Swift Package Manager

#### Option 1: Xcode GUI (Recommended)
1. Open your project in Xcode
2. Select File > Add Package Dependencies...
3. In the search field, enter: `https://github.com/zipyinc/zipy-ios-sdk.git`
4. Select the version you want to use
5. Click "Add Package"
6. Select your target and click "Add Package" again

#### Option 2: Package.swift
Add the following dependency to your `Package.swift`:
```swift
dependencies: [
    .package(url: "https://github.com/zipyinc/zipy-ios-sdk.git", from: "1.0.0")
]
```


> **Note:** Swift Protobuf will be automatically installed as a dependency when you add the ZipyiOS package.

## Initialization

For optimal performance and complete session capture, initialize the SDK as early as possible in your app's lifecycle, typically in `AppDelegate` or `SceneDelegate`. While you can integrate the SDK at any point in your application, early initialization ensures the best results and most comprehensive data collection.

### In AppDelegate:
```swift
import ZipyiOS

class AppDelegate: UIResponder, UIApplicationDelegate {
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        // Initialize Zipy SDK
        Zipy.initialize("YOUR_API_KEY")
        return true
    }
}
```

### In SceneDelegate:
```swift
import ZipyiOS

class SceneDelegate: UIResponder, UIWindowSceneDelegate {
    func scene(_ scene: UIScene, willConnectTo session: UISceneSession, options connectionOptions: UIScene.ConnectionOptions) {
        // Initialize Zipy SDK
        Zipy.initialize("YOUR_API_KEY")
    }
}
```

## Support

For issues, feature requests, or questions:
- Create an issue in the GitHub repository
- Contact our support team at support@zipy.ai
- Check the documentation for updates 