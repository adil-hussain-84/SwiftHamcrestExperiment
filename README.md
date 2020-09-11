# About

This Xcode project demonstrates that a testing target cannot build to run on a real device when [SwiftHamcrest](https://github.com/nschum/SwiftHamcrest) is added to the target via Cocoapods in the standard manner.

The Xcode build error that is omitted is as follows:

```
'/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/Library/Frameworks/XCTest.framework/XCTest' does not contain bitcode. You must rebuild it with bitcode enabled (Xcode setting ENABLE_BITCODE), obtain an updated library from the vendor, or disable bitcode for this target. file '/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/Library/Frameworks/XCTest.framework/XCTest' for architecture arm64
```

See the [Podfile](Podfile) file to see how the `SwiftHamcrest` Pod is being added to the unit testing and UI testing targets in the project. Open the [SwiftHamcrestExperiment.xcworkspace](SwiftHamcrestExperiment.xcworkspace) file in Xcode and observe that the `"Enable Bitcode"` build setting resolves to `"No"` for both the testing targets, as expected.
