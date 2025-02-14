# Expo Camera Configuration Bug

This repository demonstrates a bug in the Expo Camera API where custom camera configurations, specifically `flashMode` and `focusMode`, are not consistently applied.  The camera sometimes ignores the provided settings and defaults to its internal state. 

## Bug Reproduction

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `expo start` to start the Expo development server.
4. Observe the camera behavior.  The flash mode and focus mode may not always match the values set in the code.

## Potential Causes

* Possible race condition in the Expo Camera API's internal state management.
* Incorrect handling of asynchronous operations related to camera configuration.
* Unhandled edge cases in the API's property setting mechanism.

## Solution (see `bugSolution.js`)

A workaround involves ensuring that the camera configurations are set only after the camera is fully initialized. This can be checked using the `isCameraReady` property, although this doesn't fully resolve the underlying inconsistency.