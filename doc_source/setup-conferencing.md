# Set up Alexa Conferencing<a name="setup-conferencing"></a>

Alexa for Business enables you to dial into meetings by just using your voice\. To dial into a meeting, say “Alexa, join my meeting," If the meeting room has a supported video conferencing system, the request is sent to the third\-party Alexa skill\. The skill communicates with the video conferencing system, verifies if there is a scheduled meeting on the calendar, and prompts the user for confirmation to join the meeting\. If there is no scheduled meeting, Alexa prompts the user for the meeting ID and optionally the PIN to join their meeting\. The skill initiates a video conferencing call from the video conferencing system to the meeting\.



Alexa for Business supports the following video conferencing systems and in\-room control systems:


****  

| Device model | Requirements | 
| --- | --- | 
| Cisco/Tandberg SX, EX, DX, MX, C  | Firmware must be TC7\.3 or CE8\.0\+ | 
| Cisco Spark Room Kit | Firmware must be CE8\.0\+ | 
| Polycom Group Series | Available in beta\. To get the latest GS beta firmware to enable integration, see [Polycom and Alexa for Business Integration](http://response.polycom.com/04-DR-PS-2017-Q4-Amazon-Alexa-LP)\. | 
| Zoom Rooms |  Zoom Rooms for Mac version 4\.1\.20278\.0206 or higher Zoom Rooms for PC version 4\.1\.22620\.0319 or higher  | 
| Crestron 3\-Series | \- | 

When the room doesn’t contain any of the supported video conferencing or in\-room control systems, you can use the Echo as a speaker phone to make a PSTN call to your conferencing provider\.

When you connect Alexa for Business to your calendar system, Alexa can join scheduled meetings\. Alexa for Business can automatically detect dial\-in information from the following conferencing providers:
+ Amazon Chime
+ BlueJeans
+ Zoom
+ RingCentral Meetings
+ Cisco WebEx
+ Skype for Business
+ Fuze
+ Google Hangouts Meet \(only supported for shared devices\)