# About

This Xcode project demonstrates that a testing target cannot build to run on a real device when [SwiftHamcrest](https://github.com/nschum/SwiftHamcrest) version 2.2 is added to the target via CocoaPods in the standard manner.

The Xcode build error that is omitted is as follows:

```
'/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/Library/Frameworks/XCTest.framework/XCTest' does not contain bitcode. You must rebuild it with bitcode enabled (Xcode setting ENABLE_BITCODE), obtain an updated library from the vendor, or disable bitcode for this target. file '/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/Library/Frameworks/XCTest.framework/XCTest' for architecture arm64
```

Open the [Podfile](Podfile) to see how `SwiftHamcrest` is being added to the unit testing and UI testing targets. Open the [SwiftHamcrestExperiment.xcworkspace](SwiftHamcrestExperiment.xcworkspace) file in Xcode and observe that the `ENABLE_BITCODE` build setting resolves to `No` for both the testing targets, as expected.

An issue has been raised about this in the [SwiftHamcrest](https://github.com/nschum/SwiftHamcrest) repository [here](https://github.com/nschum/SwiftHamcrest/issues/46).
