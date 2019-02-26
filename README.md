# WebRTC UWP SDK

## Overview

This repository and the linked subrepos contains all the source and sample applications for the WebRTC UWP SDK.  For additional documentation see [webrtc-uwp.github.io](https://webrtc-uwp.github.io/).

## Cloning

From your terminal, recursively clone this repo to obtain all the source code & dependencies needed to build WebRTC for UWP:

```bash
git clone --recursive https://github.com/webrtc-uwp/webrtc-uwp-sdk
```

## Directory Structure

| Directory                | Description                                      |
| ------------------------ | ------------------------------------------------ |
| `webrtc-uwp-sdk\scripts` | scripts for preparing an environment for Windows |
| `webrtc-uwp-sdk\common`  | samples applications (AppRTC and PeerCC)         |
| `webrtc-uwp-sdk\webrtc`  | WebRTC code - builds as Org.WebRtc.dll           |
| `webrtc-uwp-sdk\docs`    | documentation                                    |

## Prerequisites

- Visual Studio 2017 (latest tested version tested 15.9.7); Community Edition is supported
- Windows SDK 17763 (available from [archive page](https://developer.microsoft.com/en-us/windows/downloads/sdk-archive))
  - When installing the SDK, include the feature **Debugging Tools for Windows** which is required by the preparation scripts. Note that the SDK installed as part of Visual Studio does not include this feature.
- C++/WinRT Visual Studio extension (available from the [VS Marketplace](https://marketplace.visualstudio.com/items?itemName=CppWinRTTeam.cppwinrt101804264))
- The minimum required Windows version to deploy apps is 1703 / Build 10.0.15063 / Anniversary Update

## Known Issues

- Due to the Windows limit on path length it is recommended to clone close to the root.  `C:\repos\my-branch` is known to work, longer paths may fail.

## Building the SDK

Several build options, including NuGet package creation, are available through command line scripts or Visual Studio.  For more information see the [webrtc-scripts](https://github.com/webrtc-uwp/webrtc-scripts) repo.  The simplest method to build the SDK and PeerCC sample in Visual Studio is described below.

1. Open the solution `webrtc-uwp-sdk\webrtc\windows\solutions\WebRtc.Universal.sln` in Visual Studio
2. Right click the `PeerConnectionClient.WebRtc` project and choose **Set as Startup Project**
3. Choose processor architecture
4. Hit F5