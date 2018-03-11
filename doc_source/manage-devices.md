# Managing Devices<a name="manage-devices"></a>

You can set up your Alexa devices \(Amazon Echo, Echo Dot, or Echo Plus\) using the Device Setup Tool\. This connects your device to your Wi\-Fi network and registers it with Alexa for Business\. After you set up your devices, you can assign them to your rooms\.

**Note**  
You need a Windows computer to use the Device Setup Tool\. You cannot run the Device Setup Tool on any cloud\-based, Windows streaming tool, such as Amazon WorkSpaces, or any imaged driver such as Boot Camp\. 

**To set up a device**

1. If you haven't already, install the Device Setup Tool\. For more information, see [Run the Device Setup Tool](getting-started.md#run-tool)\.

1. Note the last three characters of the device service number \(DSN\), printed on the box\. These characters are included in the Wi\-Fi network that the device broadcasts while you are setting it up\. They are required when you assign your device to a room\.

1. Plug your device into a power outlet, and press and hold the **Action** button \(white dot\) for five seconds\. Wait until the device tells you that it is ready and the light ring turns orange\.
**Note**  
If the device has already been set up before, you can manually enter setup mode by pressing and holding the **Action** button for 7 seconds\.

1. Open the Device Setup Tool, which discovers your device\.
**Note**  
If the Device Setup Tool doesn’t discover your devices, choose **Discover devices**\.

1. Choose the devices to set up and choose **Set up devices**\.

1. Enter your Wi\-Fi network details and choose **Next**\.

The Device Setup Tool connects your devices to your Wi\-Fi network and registers them with Alexa for Business\.

**To assign devices to a room**

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Shared devices** and select the check box next to the devices to assign to a room\.

1. Choose **Assign to room**, and choose the room to which to assign the devices\.

1. Unplug the device and plug it back in to restart it\.

We recommend that you label the devices with the room to help ensure that the device remains in the correct room\. To move devices from one room to another, unassign and then re\-assign the devices\.

**To list devices**

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Shared devices** to see a list of your registered devices and the following information for each device:

   + **Serial number** – The serial number of the device\.

   + **Type** – The type of device\. 

   + **Device name** – The name of the device\.

   + **Assigned room** – The room to which the device is assigned\.

   + **Status** – The status of the skills and settings being applied to the device\.

     + **Synced** – All skills and settings have been applied to the device\.

     + **Sync in progress** – Alexa for Business is applying the skills and settings to the device\.

     + **Sync needed** –The device was unplugged or not connected to the network when Alexa for Business was applying skills and setting to the device\.
**Note**  
To prevent your device from being offline, assign your device to a room within 24 hours of the time that you plan on plugging it into the room\. 

To avoid having a device respond to voice commands, unplug the device\. In the rare case where you no longer want to use the device anymore \(for example, if you are giving the device to a new owner\), you can deregister it\. You can register the device again with the Device Setup Tool\. Deregistering devices requires you to re\-set up devices \(otherwise, they might not work\)\.

**To deregister a device**

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Shared devices** and select the check box next to the device to deregister\.

1. Choose **Actions**, **Deregister**\.
**Note**  
This action removes the device from the console\.

You can reset a device to clear all timers, alarms, to\-do lists, shopping lists, and Bluetooth\-connected phones for a device\. This also sets the volume to 5 for a shared device\.

**To reset a device**

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Shared devices** and select the device\(s\) that you want to reset\.

1. Choose **Actions**, **Reset device**\.

Alexa for Business manages device accounts and settings through rooms and room profiles\. When you add devices to a room, change the room of a device, update specific settings in a room profile \(including the wake word, volume limit, and device setup mode\), or when you reset a device, the device must be connected to the internet for the update to complete successfully\. Alexa for Business retries these calls for one hour, and then the device is placed into a **Sync needed** status\. To implement your changes, plug in the Alexa device, ensure that it's connected to WI\-FI, and sync the device\. 

**To sync a device**

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Shared devices** and select the all the devices with the status **Sync needed** that you want to sync\.

1. Choose **Actions**, **Sync devices**\.