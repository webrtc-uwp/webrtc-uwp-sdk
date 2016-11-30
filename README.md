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
