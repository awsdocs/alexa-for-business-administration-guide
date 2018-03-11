# Getting Started with Shared Devices<a name="getting-started"></a>

After setting your IAM permissions, you can now get started with your shared devices\. The following devices can be set up as shared devices:

+ Echo \(1st and 2nd generation\)

+ Echo Dot \(2nd generation\)

+ Echo Plus


+ [Get Recommended Hardware](#get-hardware)
+ [Prepare Your Devices](#prepare-devices)
+ [Create an IAM User for Device Setup Tool](#create-IAM-user)
+ [Run the Device Setup Tool](#run-tool)
+ [Create Room Profile, Skill Group, and Room](#create-resources)

## Get Recommended Hardware<a name="get-hardware"></a>

We recommend that you obtain the following hardware to simplify the setup process:

+ Label printer or other equipment to print asset or identification tags for your devices

+ Power strips appropriately spaced for Echo or Echo Dot power adapters

+ Extra power adapters

+ Windows laptop or desktop with Wi\-Fi controller
**Note**  
The Device Setup Tool requires a Windows laptop\. It doesn't work on any virtual desktop running in the cloud or on Apple hardware\.

## Prepare Your Devices<a name="prepare-devices"></a>

There are several tips for preparing your devices before setup:

+ After you unpack a brand new device, keep the device connected for at least 15 minutes to download the latest firmware\. If your device doesn't have the latest firmware, assigning the device to a room fails\. 

+ As you unpack your devices, label them with the last three characters of the device serial numbers \(DSN\), printed on the box\. DSNs are not printed on some devices, and clearly labeling them helps you track them during setup\. You can also create asset tags that have the full DSNs and barcode on the label\.

+ You need to be within a certain distance of your devices, so we recommend that you use power strips and set them up on one or two long tables\. You can set up a maximum of 25 devices at a time\.

+ Devices stay in setup mode for only 30 minutes, and it takes about one minute to set up each device\. To ensure that the last devices to set up remain in this 30\-minute window, turn the power strips off while you plug in your devices\. Turn them back on when you’re ready to run the Device Setup Tool\. If it’s the first time they’re turned on, the devices automatically enter setup mode\.

  If the devices have been turned on previously, hold the action button on the top of the devices for 8 seconds until the light ring turns orange\. If this is the case, you may want to set up batches of fewer than 20 devices to allow for the extra time putting all devices into setup mode\.

+ If you are setting up hundreds of devices, leave the power cord for each Echo or Echo Dot plugged into the power strips and move the devices without power cords through your setup station\.

## Create an IAM User for Device Setup Tool<a name="create-IAM-user"></a>

**To create an IAM user for the Device Setup Tool**

1. Open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. Choose **Users**, **Create new users**\.

1. Enter a user name \(for example, **DeviceSetupTool**\), and choose **Programmatic access**, **Next**\.

1. Choose **Attach existing policy directly**, **AlexaforBusinessDeviceSetup** from the list, and **Next**\.

1. Choose **Create user**\.

1. Download and save the IAM access key and secret key\. You need them later when you configure the Device Setup Tool\.

## Run the Device Setup Tool<a name="run-tool"></a>

Follow these steps to run the Device Setup Tool\.

**To run the Device Setup Tool**

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Shared Devices**, **Set up devices**\.

1. Download, install, and open the Device Setup Tool\.

1. To confirm that the correct IAM access key is loaded, choose the gear icon in the upper\-right corner\.

1. Turn on the power strips or place 1–25 devices into setup mode\.

1. To generate a list of devices in setup mode, choose **Discover**\. Devices are listed as Amazon\-XXX where “XXX” is the last three characters of the DSN\.

1. Select the devices to set up\. To select all, select the check box in the device list header\.

1. Choose **Next** and enter the Wi\-Fi network information\.

1. Wait for the tool to complete\. You can monitor progress in the tool to see which device is being set up, as well as the status of each device \(**Successful** or **Failed**\)\.
**Note**  
After the status for a device changes to **Successful**, you can unplug the device even if the light ring is still orange\. If all devices show as **Failed**, make sure that you have a strong connection to the network and that the Wi\-Fi information is entered correctly\. 

After all of your devices have been set up, they are listed on the **Shared devices** page of the Alexa for Business console\. To set up more devices, repeat steps 1–7 for the additional devices\. 

## Create Room Profile, Skill Group, and Room<a name="create-resources"></a>

After you set up your devices with the Device Setup Tool, you are ready to create the following resources:

+ [A room](manage-rooms.md)

+ [A room profile](manage-profiles.md)

+ [A skill group](manage-skill-groups.md)