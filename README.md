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

Known issues:
----------------------------
* ARM is currently not working.
* Choosing audio playback / recording devices not working.

Troubleshooting:
----------------------------
 * The first project must be built WebRtc.Builder.
 * Checkout windows line ending in "webrtc-uwp-sdk \ bin" otherwise prepare and build scripts (bat files) will not work. And commit with unix line endings. (git config - global core.autocrlf true - checkout windows, commit unix)
 * Webrtc requires VS 2015 Win 10 SDK 14. *
 * There is no build dependency when you change WebRTC sources (not meaning UWP wrapper) so you have to run rebuild on WebRtc.Builder manually.
  * When you want to build your own project based on WebRTC UWP SKD you have to add to your main executable project these lines:
  `` `
      <Content Include = "<your relative path prefix eg .. \ .. \ .. \ .. \ .. \> \ webrtc \ xplatform \ webrtc \ WEBRTC_BUILD \ webrtc \ $ (Configuration) dll ">
      <Link> boringssl.dll </ link>
    </ Content>
    <Content Include = "<your relative path prefix eg .. \ .. \ .. \ .. \ .. \> \ webrtc \ xplatform \ webrtc \ WEBRTC_BUILD \ webrtc \ $ (Configuration) dll ">
      <Link> protobuf_lite.dll </ link>
    </ Content>
  `` `
