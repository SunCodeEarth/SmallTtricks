# Geospatial VR on the Web

Discuss virtual reality options and solutions for geospatial data.

## Join the big players

Steam: the gamers' home created by Valve, where gamers purchase, play, and discuss games. 
HTC: an IT company mainly focusing on hardware. 
HTC Vive: a VR headset and system developed by Valve and HTC. 
Steam VR: an extension of Steam for VR games by Valve. Natually, it works best with HTC Vive. 

From there, things are getting complex. Valve wants to make SteamVR more device-independent so other VR devices such as Oculus Rift can also use it as a game platform. SteamVR is also on the way to OpenVR or Open Source VR. No surprise, HTC is also going another way by creating its own ViveVR platform with store for games and apps.  

Other VR Devices and systems basically follow the same route: compatible with Steam but also have their own ecosystems. 

## Firefox Reality, WebVR, and WebXR

Firefox Reality: A web browser live inside VR, i.e., people can surf the internet using VR on Firefox Reality. It is just a web brower app on VR platform.
WebVR: A JavaScript-based API to support VR directly in Firefox. It will be evolve to WebXR.
WebXR: The developing Web Mixed Reality API, which expands WebVR to allow augumented reality, audio, etc. 

I am not a gamer, at least not like most gamers on Steam. I am just looking for ways to visualize data, particularly geospatial data. It is also the Internet age with tremendous openness. So, I prefer to use the more open WebVR, WebXR to create visual representations for geospatial data. One advantage of WebXR is that the visuals are also good without VR headsets. And the two stereo graphs are also visible on the screen in VR mode, which is handy for development, debug, and illustation purposes.

### Error: Firefox failed to create WebGL 2.0

Sometimes, Firefox has trouble create WebGL 2.0 with errors like ```WebGL: Disallowing antialiased backbuffers due to blacklisting```. Solution: 1) allow antialiasing in NVIDIA Settings or NVIDIA Control Panel (assume you are using a good GeForce graphic card for VR) --> Manage 3D Settings --> Program Settings --> Firefox --> Antialiasing. 2) Firefox about:config webgl force enable --> true. Use either one both to fix the problem.

## WebGL and Three.js 
 
So far, I have decided the hardware and platform problems, i.e., HTC VIVE and Mozilla WebVR/WebXR. Now, it comes the most important part: content or model builder. Fot Web-based VR, WebGL is a must-have. And three.js seems like a good environment for connecting WebGL to GIS/geospatial data.

### Good resources to start with
- three.js based <br>
  - https://github.com/datadesk/vr-interactives-three-js <br>
  - https://blog.mozvr.com/tag/threejs/  <br>

* geospatial solutions based on three.js <br>
  - https://github.com/iTowns/itowns  <br>
  - https://github.com/UDST/vizicities <br>

* A-Frame: three.js framework optimized for webvr <br>
  - https://aframe.io/ <br>
  - https://blog.mozvr.com/introducing-a-terrain/ <br>

* WebGL for Geospatial <br>
  - Uber deck.gl
  - Mapbox GL


