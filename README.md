# Segment-Firebase

[![CircleCI](https://circleci.com/gh/segment-integrations/analytics-ios-integration-firebase.svg?style=svg)](https://circleci.com/gh/segment-integrations/analytics-ios-integration-firebase)
[![Version](https://img.shields.io/cocoapods/v/Segment-Firebase.svg?style=flat)](http://cocoapods.org/pods/Segment-Firebase)
[![License](https://img.shields.io/cocoapods/l/Segment-Firebase.svg?style=flat)](http://cocoapods.org/pods/Segment-Firebase)
[![Platform](https://img.shields.io/cocoapods/p/Segment-Firebase.svg?style=flat)](https://cocoapods.org/pods/Segment-Firebase)

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Requirements

## Installation

Segment-Firebase is currently only available through [CocoaPods](http://cocoapods.org).

Register your app in the [Firebase console](https://console.firebase.google.com/) and add the `GoogleService-Info.plist` to the root of your Xcode project.

Add the following dependency to your Podfile:

 ```
 pod 'Segment-Firebase'
 ```

After adding the dependency and running `pod install`, import the integration:

```
#import <Segment-Firebase/SEGFirebaseIntegrationFactory.h>
```

Finally, register the dependency with the Segment SDK:

```
[config use:[SEGFirebaseIntegrationFactory instance]];
```

By default, Segment only bundles `Firebase/Core` which is [Firebase's Analytics offering](https://firebase.google.com/docs/analytics/). You can see the other available [Firebase pods and features here](https://firebase.google.com/docs/ios/setup).

## Troubleshooting

For users who are unable to bundle static libraries as dependencies (Swift project for example) you can choose `StaticLibWorkaround` subspec, but be sure to include `Firebase/Core` in your Podfile:

Example:

```ruby
  pod 'Firebase/Core', '~> 4.0'
  pod 'Segment-Firebase/StaticLibWorkaround'
```

Next step, add manually 4 files to your project (located under `<YOUR_APP>/Pods/Segment-Firebase/Classes/`):

 - `SEGFirebaseIntegration.h`
 - `SEGFirebaseIntegration.m`
 - `SEGFirebaseIntegrationFactory.h`
 - `SEGFirebaseIntegrationFactory.m`

Xcode will ask you to generate `<YOUR_APP_NAME>-Bridging-Header.h`
Add to this file `#import "SEGFirebaseIntegrationFactory.h"`

For more details follow the instructions from Apple [here](https://developer.apple.com/library/content/documentation/Swift/Conceptual/BuildingCocoaApps/MixandMatch.html).

## License

Segment-Firebase is available under the MIT license. See the LICENSE file for more info.
