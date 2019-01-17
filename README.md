INSTRUCTIONS
=======

From your terminal, recursively clone this repo to obtain all the source code needed to build WebRTC for UWP:
git clone --recursive https://github.com/webrtc-uwp/webrtc-uwp-sdk.git

This repository will yield the WebRtc SDK and dependency libraries.

Directory structure:

- webrtc-uwp-sdk\bin          	contains scripts for preparing an environment for the Windows
- webrtc-uwp-sdk\common         contains samples applications (ChatterBox and PeerCC)
- webrtc-uwp-sdk\webrtc    		contains WebRtc code
- webrtc-uwp-sdk\docs			contains documentation

Prerequisites:

- Visual Studio 2017 (latest tested version tested 15.6)
- Windows SDK 16299 (available from archive page https://developer.microsoft.com/en-us/windows/downloads/sdk-archive)
- When installing the SDK, include the feature "Debugging Tools for Windows" which is required to run prepare.bat. Note that the SDK install as part of Visual Studio does not include this feature.


How to Build:

WINDOWS BUILD :
----------------------------

1) Run prepare script, from your terminal:
<br />
<pre>
<code>
cd webrtc-uwp-sdk
bin\prepare.bat
</code>
</pre>
<br />
This script will prepare environment but it won't build webrtc projects. In this case webrtc project will be built from Visual Studio once you try to build Org.WebRtc.

2) From VS2015, load webrtc\windows\solutions\WebRtc.sln for WebRtc development.

3) Now you can build winrt libraries for WebRtc and deploy sample apps ChatterBox and PeerCC.

====

# Unity Video Rendering on HoloLens

## Unity build requirements

* Unity version 2018.2.13 (2018.2.13f1) with IL2CPP Scripting Backend

## Running Unity Peer Connection Client application on HoloLens device 

1. Open `webrtc\windows\solutions\WebRtcUnity.sln` solution, select x86 platform and build PeerConnectionClientUnityCore project. The build procedure produces WebRTC libraries, WebRTC for UWP wrapper component and deploys WebRTC and Peer Connection Client Core libraries to the Unity project space.
2. Open Unity project `common\windows\samples\PeerCC\ClientUnity' in Unity Editor
3. Go to 'File' -> 'Build settings...', select 'Universal Windows Platform', click on the 'Build' button and choose an export folder
4. Add the following XML block to generated manifest file `PeerCCUnity\Package.appxmanifest`:
```
  <Extensions>
    <Extension Category="windows.activatableClass.inProcessServer">
      <InProcessServer>
        <Path>WebRtcScheme.dll</Path>
        <ActivatableClass ActivatableClassId="WebRtcScheme.SchemeHandler" ThreadingModel="both" />
      </InProcessServer>
    </Extension>
  </Extensions>
```
5. Open PeerCCUnity.sln from export folder, build PeerCCUnity project and run the application on the device 
