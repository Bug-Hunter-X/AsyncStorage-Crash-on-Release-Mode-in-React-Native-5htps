# AsyncStorage Crash on Release Mode in React Native

This repository demonstrates a bug where AsyncStorage in React Native crashes silently in release mode but works correctly in debug mode.  The issue is difficult to debug due to the lack of a clear error message.

## Bug Description

The app crashes when attempting to retrieve data from AsyncStorage after being built in release mode.  No helpful error messages are provided in the console or via crash reports.  Debugging in debug mode reveals no errors, making identification of the root cause challenging.

## Reproduction Steps

1. Clone the repository.
2. Run `npx react-native run-android` (or iOS equivalent) in debug mode.  The app should work without issues.
3. Build a release version of the app and install it on a physical device or emulator.
4. Attempt to access data from AsyncStorage. The application will likely crash without providing an error message.

## Solution

The provided solution file `bugSolution.js` addresses the issue by adding robust error handling to the AsyncStorage calls, including a `try-catch` block to catch any exceptions and logging mechanisms to provide more informative error messages even in release builds.