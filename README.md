# Expo Linking.getInitialURL() Inconsistently Returns Null

This repository demonstrates a bug where `Linking.getInitialURL()` in the Expo SDK returns `null` even when a deep link was used to launch the application. This is particularly unreliable on Android.

## Bug Description

The `Linking.getInitialURL()` method is crucial for handling deep links.  Inconsistent `null` returns break the core functionality of handling deep links, leaving the app in an unexpected state.  This problem affects the user experience by not allowing the app to react appropriately to deep links.

## How to Reproduce

1. Clone this repository.
2. Run the app on both Android and iOS emulators/devices.
3. Open a deep link to the app (the specific link is defined in the code). Observe the results, with particular attention to Android inconsistencies.

## Expected Behavior

`Linking.getInitialURL()` should consistently return the deep link URL used to launch the app.

## Actual Behavior

On Android, `Linking.getInitialURL()` frequently returns `null`, even when a valid deep link was used to launch the app.  iOS is more reliable but isn't guaranteed to always work as expected.

## Solution

A robust solution is provided in `bugSolution.js` which uses a combination of event listeners and improved error handling.