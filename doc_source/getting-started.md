# Get started with Alexa for Business shared devices<a name="getting-started"></a>

After setting your IAM permissions, you can now get started with your shared devices\. The following devices can be set up as shared devices:
+ Echo \(1st, 2nd, 3rd, and 4th generation\)
+ Echo Dot
  + 2nd, 3rd, and 4th generation
  + 3rd generation with clock and 4th generation with clock
+ Echo Plus \(1st, and 2nd generation\)
+ Polycom Trio 8500 and 8800
+ Lifesize Icon 300, 500, and 700
+ Amazon Chime on Dolby Voice Room 

**Topics**
+ [Get recommended hardware](#get-hardware)
+ [Prepare your devices](#prepare-devices)
+ [Create network profile](#network-profile)
+ [Import your devices](#import)
+ [Create room profile, skill group, and room](#create-resources)

## Get recommended hardware<a name="get-hardware"></a>

We recommend that you obtain the following hardware to simplify the setup process:
+ Label printer or other equipment to print asset or identification tags for your devices
+ Power strips appropriately spaced for Echo or Echo Dot power adapters
+ Extra power adapters
+ Windows laptop or desktop with Wi\-Fi controller

## Prepare your devices<a name="prepare-devices"></a>

There are several tips for preparing your devices before setup:
+ After you unpack a brand new device, keep the device connected for at least 15 minutes to download the latest firmware\. If your device doesn't have the latest firmware, assigning the device to a room fails\. 
+ As you unpack your devices, label them with the last three characters of the device serial numbers \(DSN\), printed on the box\. DSNs are not printed on some devices, and clearly labeling them helps you track them during setup\. You can also create asset tags that have the full DSNs and barcode on the label\.
+ You need to be within a certain distance of your devices, so we recommend that you use power strips and set them up on one or two long tables\.
+ If it’s the first time they’re turned on, the devices automatically enter setup mode\. If the devices have been turned on previously, hold the action button on the top of the devices for 8 seconds until the light ring turns orange\.
+ If you are setting up hundreds of devices, leave the power cord for each Echo or Echo Dot plugged into the power strips and move the devices without power cords through your setup station\.

## Create network profile<a name="network-profile"></a>

To create, assign, and manage network settings for your shared Echo devices, see [Manage network profiles](manage-network-profiles.md)\. Network profiles enable you to manage wireless password rotations and enterprise certificate rotations\.

**Note**  
We recommend setting up your shared Echo devices on a dedicated network created for IoT devices\.

## Import your devices<a name="import"></a>

Use the Alexa Companion app to set up your devices using your Amazon\.com or Amazon Business account, then import your devices into Alexa for Business\. 

Follow these steps to import your devices into Alexa for Business using the Alexa Companion app\.

**To import your devices**

1. Sign in to the Alexa Companion app using your Amazon\.com or Amazon Business account credentials\.

1. Set up your devices by following the instructions in the Alexa Companion app\.

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Shared devices**\.

1. Choose **Import devices**\.

1. Sign in with the same Amazon\.com or Amazon Business credentials that you used to sign in to the Alexa Companion app\.

1. For **Choose device\(s\)**, select the Echo devices to be imported in Alexa for Business, and choose **Import**\.

We recommend associating the network profile with your corporate network credentials to the devices you just imported\. For more information, see [Manage network profiles](manage-network-profiles.md)\.

After your devices are set up, they are listed on the **Shared devices** page of the Alexa for Business console\. 

## Create room profile, skill group, and room<a name="create-resources"></a>

You are now ready to create the following resources:
+ [A room](manage-rooms.md)
+ [A room profile](manage-profiles.md)
+ [A skill group](manage-skill-groups.md)