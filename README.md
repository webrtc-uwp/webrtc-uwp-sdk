# Instructions

From your terminal, recursively clone this repo to obtain all the source code needed to build WebRTC for UWP:
git clone --recursive https://github.com/webrtc-uwp/webrtc-uwp-sdk.git

This repository will yield the WebRtc SDK and dependency libraries.

Directory structure:

- webrtc-uwp-sdk\bin          	contains scripts for preparing an environment for the Windows
- webrtc-uwp-sdk\common         contains samples applications (ChatterBox and PeerCC)
- webrtc-uwp-sdk\webrtc    		contains WebRtc code
- webrtc-uwp-sdk\docs			contains documentation

Prerequisites:

- Visual Studio 2017 (latest tested version tested 15.8.1)
- Windows SDK 17134 (available from archive page https://developer.microsoft.com/en-us/windows/downloads/sdk-archive)
- When installing the SDK, include the feature "Debugging Tools for Windows" which is required to run prepare.bat. Note that the SDK install as part of Visual Studio does not include this feature.
- The minimum required Windows version to deploy apps is 1703 / Build 10.0.15063 / Anniversary Update

Known Issues:
- ARM is currently unsupported (but under development).  For ARM support, use M54 or earlier releases.
- Audio device selection was removed from the Google WebRTC APIs, and is therefore no longer supported here.  Playback occurs on the default device as specified by Windows.
- Due to the Windows limit on path length it is recommended to clone close to the root.  C:\repos\my-branch is known to work, longer paths may fail.

## Windows Build

1. Run prepare script, from your terminal:
<br />
<pre>
<code>
cd webrtc-uwp-sdk
bin\prepare.bat
</code>
</pre>
<br />
This script will prepare environment but it won't build webrtc projects. In this case webrtc project will be built from Visual Studio once you try to build Org.WebRtc.

2. From VS2017, load webrtc\windows\solutions\WebRtc.sln for WebRtc development.

3. Now you can build UWP libraries for WebRtc and deploy sample app PeerCC.
