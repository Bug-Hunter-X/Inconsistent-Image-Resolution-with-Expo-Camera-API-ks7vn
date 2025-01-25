# Inconsistent Image Resolution with Expo Camera API

This repository demonstrates a bug in the Expo Camera API where the returned image resolution is inconsistent, even when explicitly setting a custom resolution. The issue occurs across different devices and operating systems.

## Bug Description

The `Expo.Camera` component does not always return images with the expected dimensions as specified in the `resolution` prop. This unpredictability poses significant challenges when building applications that rely on precise image sizes for processing, uploading, or display.

## Reproduction Steps

1. Clone this repository.
2. Install dependencies: `npm install`
3. Run the app: `expo start`
4. Capture images using the app. Note the inconsistency in image dimensions despite the specified resolution.

## Expected Behavior

The captured images should consistently match the specified resolution set in the `resolution` prop.

## Actual Behavior

The captured images often have dimensions different from what was set, leading to unexpected behavior in downstream image processing.

## Solution

A potential workaround is to check the actual dimensions of the captured image after capturing and adjust image handling accordingly (see `bugSolution.js`).  However, a robust solution would require a fix in the Expo Camera API to consistently return the requested resolution.

## Additional Context

The issue has been observed on both iOS and Android devices.