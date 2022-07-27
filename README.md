# VRC-MultiOSC

*Notice: as I nolonger use the VRC software/platform no further update will be provided to this content*

The VRC OSC implimentaion can support many apps sending data in (via port 9000), but only allows for one binding (port 9001) for outboud info.  

## Solution - use an OSC router
List:  
- https://github.com/SutekhVRC/VOR

## Setup

### apps
#### VOR
Add one app section per OSC app that needs to recive info (eg https://github.com/benaclejames/VRCFaceTracking, https://github.com/HerpDerpinstine/bHapticsOSC)  
![image](https://user-images.githubusercontent.com/31048789/180659384-4e32646c-8525-486a-a4f7-fe2da447670e.png)  
note that the port you want to connect your OSC receving apps to is the `App Port` not the `Bind Port`  

#### BhapticsOSC
Edit the `Connection.cfg` file and set the Port in the OscReceiver section to match the App Port you set in VOR  

#### VRCFaceTracking (OSC)
When you launch the app, ensure that you add the perameter section for custom OSC config eg. `VRCFaceTracking.exe --osc=9000:127.0.0.1:9200`  

### Order of startup example
apps list:  
- VRC
- VOR
- PiTool
- Steam VR
- SRanipalRuntime
- VRCFaceTracking
- bHapticsOSC
- bHapticplayer
- HRtoVRChat_OSC_UI

 
Start PiTool and ensure all trackers/Controlers are detected (headset should be showing green π )  
![image](https://user-images.githubusercontent.com/31048789/180659952-0b87ef44-1d7a-40b6-b8a8-834e5e2ae608.png)  
Start SteamVR and ensure all devices are listed  
![image](https://user-images.githubusercontent.com/31048789/180659986-808f9718-da59-4001-a362-c21307eb4aca.png)  
Start SRanipalRuntime, enure it starts and can see your tracker cams  
![image](https://user-images.githubusercontent.com/31048789/180660019-d6b86f4e-8057-4dbb-9583-ca856cc08863.png)  
Start bHaptics player and power on/connect your haptic devices  
![image](https://user-images.githubusercontent.com/31048789/180660165-29878a06-9957-482c-89c3-b9668d540a13.png)  
Start VRC and wait for it to fully load into your homeworld  
Start VOR  
![image](https://user-images.githubusercontent.com/31048789/180660217-05812366-dce2-431b-ad3f-57ee7d0219f2.png)  
Start VRCFaceTracking and test on your avatar  
![image](https://user-images.githubusercontent.com/31048789/180660339-b6773ba0-a1ce-4b03-adf7-dbf8a321c87f.png)  
(note I am running a slightly custom app version with more logging output)  
Start HRtoVRChat_OSC_UI (along with whatever you feed it with), and check the feed is working  
![image](https://user-images.githubusercontent.com/31048789/180660454-92cd2aac-5002-4988-9f78-b308d6609c05.png)  
Start bHapticsOSC and test touch contacts work  
![image](https://user-images.githubusercontent.com/31048789/180660544-6eeb3214-3eed-41a9-bf77-10c70c8fd7fe.png)  


#### Common issues
issue: OSC inputs not woking in game/showing on OSC debu pannel  
fix: issue the `Reset Config` command in the OSC radial menu  
![image](https://user-images.githubusercontent.com/31048789/180660649-70a804f9-d28a-4475-9e20-aae437374838.png)  






