# Troubleshoot Zoom Rooms<a name="zoom-troubleshoot"></a>

If you experience any of the following issues using Zoom Rooms with Alexa for Business, try these workarounds to resolve your problem\.
+ ***Alexa responds "I can't join the meeting, please contact your IT support"\. ***

  When you get this response, there is probably an issue where the Zoom Alexa skill can't communicate with the Zoom Rooms API to control your Zoom Room\.

  To validate the configuration of your Zoom Alexa skill, follow these steps:

  1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

  1. Choose **Rooms** and select the room name where you got the error response\.

  1. In the **Skills** section, find the name of your Zoom Room\.
**Note**  
If you don't see the name of your Zoom Room, choose the edit icon and enter the Zoom Room name\. Choose **Smart Home devices**, **Forget devices**, and then **Discover devices**\. If **Discover devices** is unavailable, Alexa is still processing the settings made to your skill\. 
+ ***Alexa doesn't show me a list of Zoom Rooms when I try to register a new device\.***

  To activate Alexa for your Zoom Room, you must select the room where you want to enable Alexa\. Alexa for Business retrieves a list of all Zoom Rooms from your Zoom account\. If no rooms are shown in the drop\-down list, make sure that your Zoom Room admin has a Zoom Business, Education, or Enterprise plan\.
**Note**  
Zoom Room admin accounts with a Zoom Professional plan are currently not supported\. 
+ ***I can't find my Alexa for Business logs\.***

  Logs for the Alexa for Business app are created in the location C:\\Users\\o\\AppData\\Local\\AWS\\A4B\.
+ ***Alexa is giving the wrong time/weather\.***

  For information about how to change these settings, see [Change Alexa for Business settings for your Zoom Rooms](zoom-settings.md)\.
+ ***My activation code is invalid\. ***

  When you activate Alexa for your Zoom Room, a 6\-digit activation code is displayed in the Alexa for Business app\. The activation code is only valid for 10 minutes\. If activation fails, you can generate a new activation code by using the refresh button in the Alexa for Business app\. 