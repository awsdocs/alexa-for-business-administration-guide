# Use Poly Trio with Alexa for Business<a name="using-poly-trio"></a>

The latest firmware for Poly Trio has integrated natively with Alexa Voice Service and lets you use Alexa in your meeting rooms\. With Alexa on Poly Trio, you can make hands\-free phone calls, join meetings, check meeting room availability, book or find a meeting room for your meeting, and access private skills, such a company briefing or company FAQs\. For more information, see [Poly Trio Systems with Alexa for Business Deployment Guide](https://documents.polycom.com/bundle/alexa-for-business-dg-current/page/c3172515.html)\.

To use Alexa on Poly Trio devices, you must meet the following requirements:
+ Firmware 5\.9\.0 or higher must be installed on your Poly Trio devices\.
+ Your Poly Trio must be registered with the Poly Cloud Service\. To get your Poly Cloud Service tenant created, contact your Poly sales representative, or go to [https://www.polycom.com/forms/pdms-e-trial.html](https://www.polycom.com/forms/pdms-e-trial.html)\. 

**To use Poly Trio with Alexa for Business**

1. Set up AVS permissions\.

   To grant Poly permissions to register your Trio devices into your AWS account and assign them to a room, you must create an IAM service role\. 

   If your IAM user account, group, or role is assigned administrator or PowerUserAccess permissions, then you have all the permissions to set up Alexa for Business\. If you don't have administrator permissions, then an AWS account administrator must update your IAM user account, group, or role to include PowerUserAccess permissions or perform the following steps for you\. 

   1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

   1. Choose **Settings**, **AVS permissions**\.

   1. Choose **Poly** from the drop\-down menu and choose **Create IAM role**\.

   1. Download the CSV file\. You'll need to upload this file in the Poly Cloud Service in a future step\.

1. Set up your conferencing provider\.

   To have Alexa for Business join your meetings, you must set up your conferencing provider\. Alexa for Business offers a list of built\-in conference providers, including Amazon Chime, BlueJeans, Cisco Webex, Skype for Business, and Zoom\. Alexa for Business uses the conference provider settings to build the dial sequence when joining a meeting\. For more information, see [Manage conferencing providers](manage-providers.md)\.

   1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

   1. Choose **Conferencing** and **Add provider**\. 

   1. Choose the conferencing provider that you are using in your organization, and enter the PTSN dial\-in number and SIP endpoint\. 

1. Link your calendar\.

   To join scheduled meetings, check room availability, and book a room for a meeting by asking Alexa, you must link your calendar to Alexa for Business\.

   Alexa for Business supports Microsoft Exchange, Microsoft Office365, and Google G\-Suite\. For more information, see [Link Alexa for Business to your calendar system](manage-calendaring.md)\.
**Note**  
Although your Poly Trio might be connected to your calendar system to provide one\-touch join, the locally linked calendar won’t be used by Alexa\.

1. Enable skills and add them to a skill group\.

   Skills are voice\-driven capabilities that enhance the functionality of your Alexa device\. Alexa for Business gives you access to all skills in the Alexa Skills store\. You can also build skill specifically for your organization by using Blueprints or developing a private skill\. 

   To enable skills for your devices, you must first enable the skill for your organization and then add it to one or more skill groups that are assigned to your rooms\. For more information, see [Manage skill groups](manage-skill-groups.md) and [Manage skills](manage-skills.md)\.

1. Create a room profile\.

   To simplify the process of creating and managing rooms, first define room profiles\. A room profile contains the settings for your Alexa devices, so that they can provide you with weather, time, and other location\-based information\. For example, you can create a room profile that contains the Alexa settings that apply to all rooms in the same building\.

1. Prepare your Poly Trio device\.

   To use Alexa for Business on your Poly Trio, you must register your Poly Trio through PDMS\-E with Alexa for Business\. Before you can register your Poly Trio, first Enable the Universal Agent \(formerly known as Poly Cloud Connector or PCC\)\. The Universal Agent must onboard your Poly Trio to PDMS\-E, even if you’re onboarding Poly Trio using the MAC address\.

   Before you begin using the following steps, make sure that you have configured your Network Time Protocol server with Poly Trio\. 

   1. Copy the following XML information into a text file and save it as a \.cfg file \(for example, pcc\.cfg\)\. 

      ```
      <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
      <UPLOAD>
      <ALL
      feature.pcc.enabled="1"
      feature.da.enabled="1"
      />
      </UPLOAD>
      ```

   1. Log in to the Poly Trio Web Interface as an administrator\.

   1. Choose **Utilities**, **Import & Export Configuration**, **Choose File**, and select the \.cfg file generated \(for example, pcc\.cfg\) to enable Universal Agent\. 

   1. To enable Alexa for Business for your Poly Trio, copy the following XML information into a text file and save it as a \.cfg file \(for example, alexa\.cfg\)\. 
**Note**  
You can also enable these settings using your existing management and provisioning solution, such as Poly Resource Manager\.

      ```
      <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
      <upload>
      <ALL
      feature.alexaForBusiness.enabled="1"
      feature.alexaForBusiness.HandsFree.enabled="1"
      /> </UPLOAD>
      ```

   1. Log in to the Poly Trio Web Interface as an administrator\.

   1. Choose **Utilities**, **Import & Export Configuration**, **Choose File**, and select the \.cfg file generated \(for example alexa\.cfg\)\. 

   1. After the device restarts, a gray Alexa icon appears at the bottom of the Trio display\. 

1. Set up Alexa for Business in PDMS\-E\.

   To enable Alexa on your Poly Trio devices, you must first register them into Alexa for Business\. Registration is done through Poly Device Management Service \(PDMS\-E\)\.

   1. Go to [https://console.plcm.cloud](https://console.plcm.cloud) and sign in using the credentials provided by Poly\.

   1. Choose **Alexa for Business**, enable Alexa for Business, upload the CSV file your created in step 1, and choose **Save**\.

1. Add your Poly Trio devices to PDMS\-E\.

   To enable Alexa for Business on your Poly Trio device, first make sure that the latest 5\.9 firmware is installed\.

   1. Go to [https://console.plcm.cloud](https://console.plcm.cloud) and sign in using the credentials provided by Poly\.

   1. Choose **PDMS\-E**, **Device Monitor**, **Add**, **RealPresence Trio**, and select the check box for **Cloud registration**\.

   1. Log in to the Poly Trio Web Interface as an administrator, choose **Diagnostics** and **Cloud Services**, and make note of the registration key\.

   1. Enter the registration key into the **Registration code** field\.

   1. Choose your Poly Trio model and enter a device name\. 

   1. Choose **Save** to complete device registration\. 

   1. The newly added Poly Trio appears on the **Device Monitor** page and all status icons appear grayed out\.

   1. To finalize setup, assign your Poly Trio to an Alexa for Business room:

      1. Choose the Device name \(Poly Trio only\) that you want to assign to an Alexa for Business Room\. 

      1. Choose the **Alexa for Business** tab, select one of the existing Alexa for Business rooms \(or create a new one\), and choose **Save**\.
**Note**  
You can also do this in the Alexa for Business console\.

   1. Your device is now successfully registered to Alexa for Business and assigned to a room\. Within couple of minutes, you will see the Alexa icon on the Trio UI turn blue\. Alexa is now active and can be used by either saying the wake word or by pushing on the Alexa icon\. 

   1. In the Alexa for Business console, you can view all of your Poly Trio devices that have Alexa for Business enabled, manage Alexa settings, and enable new skills\.