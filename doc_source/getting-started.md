# Getting Started with Shared Devices<a name="getting-started"></a>

After setting your IAM permissions, you can now get started with your shared devices\. The following devices can be set up as shared devices:
+ Echo \(1st and 2nd generation\)
+ Echo Dot \(2nd generation\)
+ Echo Plus

**Topics**
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
+ You need to be within a certain distance of your devices, so we recommend that you use power strips and set them up on one or two long tables\.
+ If it’s the first time they’re turned on, the devices automatically enter setup mode\. If the devices have been turned on previously, hold the action button on the top of the devices for 8 seconds until the light ring turns orange\.
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

1. Download, install, and open the [Device Setup Tool](https://s3.amazonaws.com/device-setup-tool/setup.exe) on a Windows computer enabled with Wi\-Fi\.
**Note**  
By downloading the Device Setup Tool, you agree to the [AWS Customer Agreement](https://aws.amazon.com/agreement/) and [AWS Service Terms](https://aws.amazon.com/service-terms/)\. If you already have an AWS customer agreement, you agree that the terms of that agreement govern your download and use of this product\.

1. From the home page of the application, choose **Get started**\.

1. Enter the IAM access key and secret access key that you created for the Device Setup Tool user, and choose **Next**\.

1. Enter the Wi\-Fi information of the network to connect to your Alexa devices\. 

1. Enter the Wi\-Fi information of the network to connect to your computer during setup, and choose **Next**\.
**Note**  
To change this information later, choose **Change Wi\-Fi** from the **Device setup** home page\.

1. Put your Alexa devices into setup mode by powering them on for the first time, or by holding the action button on the top of the Echo device\.

1. From the **Device setup** home page, choose **Start setup** to scan for all Alexa devices in setup mode nearby and register them to your Alexa for Business organization\.
**Note**  
If you don't want to set up all Alexa devices in setup mode near your computer, choose **Select devices** and select from the list the devices to set up\. To download a \.csv file with the MAC address for your selected devices, choose **Download MAC info**\. 

1. Wait for the tool to complete\. You can monitor progress in the tool to see which device is being set up, as well as the status of each device \(**Successful** or **Failed**\)\.
**Note**  
After the status for a device changes to **Successful**, you can unplug the device even if the light ring is still orange\. If all devices show as **Failed**, make sure that you have a strong connection to the network and that the Wi\-Fi information is entered correctly\. 

After all of your devices have been set up, they are listed on the **Shared devices** page of the Alexa for Business console\. To set up more devices, repeat steps 1–8 for the additional devices\. 

## Create Room Profile, Skill Group, and Room<a name="create-resources"></a>

After you set up your devices with the Device Setup Tool, you are ready to create the following resources:
+ [A room](manage-rooms.md)
+ [A room profile](manage-profiles.md)
+ [A skill group](manage-skill-groups.md)