INSTRUCTIONS
=======

From your terminal, recursively clone this repo to obtain all the source code needed to build WebRTC for UWP:
git clone --recursive https://github.com/webrtc-uwp/webrtc-uwp-sdk.git

This repository will yield the WebRtc SDK and dependency libraries.

Directory structure:

- webrtc-uwp-sdk\bin          	(DEPRECATED) contains scripts for preparing an environment for the Windows
- webrtc-uwp-sdk\common         contains samples applications (ChatterBox and PeerCC)
- webrtc-uwp-sdk\webrtc    		  contains WebRtc code
- webrtc-uwp-sdk\docs			      contains documentation
- webrtc-uwp-sdk\scripts        contains scripts for preparing dev environment, building and creating webrtc nuget package

Prerequisites:

- Visual Studio 2017 (latest tested version tested 15.6)
- Windows SDK 16299 (available from archive page https://developer.microsoft.com/en-us/windows/downloads/sdk-archive)
- When installing the SDK, include the feature "Debugging Tools for Windows" which is required to run prepare.bat. Note that the SDK install as part of Visual Studio does not include this feature.


How to Build:

WINDOWS BUILD :
----------------------------

1) From VS2017, open webrtc\windows\solutions\WebRtc.Universal.sln for WebRtc development.

2) In VS2017 go to Tools > Options > Projects and Solutions > General and uncheck “Allow parallel project initialization”.

3) Now you can build WebRtc Windows Universla library and run PeerCC sample app.

====
