# Use Lifesize room systems with Alexa for Business<a name="lifesize"></a>

You can use Alexa for Business with Lifesize room systems\. Alexa is supported on Lifesize Phone HD when connected to a Lifesize Icon 300, 500, or 700 device\. With Alexa on Lifesize room systems, you can make hands\-free calls, join meetings, check meeting room availability, book or find a meeting room for your meeting, and access private skills, such as a company briefing or company FAQs\. For more information, see [https://www.lifesize.com/en/help/admin-console/manage-room-systems/alexa-for-business-configuration](https://www.lifesize.com/en/help/admin-console/manage-room-systems/alexa-for-business-configuration)\. 

**To set up Lifesize room systems with Alexa for Business**

1. Set up Alexa Voice Service \(AVS\) permissions\.

   To grant Lifesize permissions to register your Lifesize room systems into your AWS account and assign them to a room, you must create an AWS Identity and Access Management \(IAM\) service role\. 

   If your IAM user account, group, or role is assigned administrator or PowerUserAccess permissions, then you have all the permissions necessary to set up Alexa for Business\. If you don't have administrator permissions, then an AWS account administrator must update your IAM user account, group, or role to include PowerUserAccess permissions or perform the following steps for you\. 

   1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

   1. Choose **Settings**, **AVS permissions**\.

   1. Choose **Lifesize** from the drop\-down menu and **Create IAM role**\.

   1. Download the CSV file\. You will upload this file in the Lifesize admin portal in a later step\.

1. Create a room profile\.

   To simplify the process of creating and managing rooms, define room profiles\. A room profile contains the settings for your Alexa devices, so that they can provide you with weather, time, and other location\-based information\. For example, you can create a room profile that contains the Alexa settings that apply to all rooms in the same building\. For more information, see [Manage room profiles](manage-profiles.md)\. 

1. Link your calendar\.

   To join scheduled meetings, check room availability, and book a room for a meeting by asking Alexa, you must link your calendar to Alexa for Business\.

   Alexa for Business supports Microsoft Exchange, Microsoft Office 365, and Google G Suite\. For more information, see [Link Alexa for Business to your calendar system](manage-calendaring.md)\.

1. Link your AWS account to your Lifesize account\.

   To register a Lifesize room system with Alexa for Business, you must first grant access through your Lifesize account\. 

   1. Sign into the [Lifesize admin console](https://manage.lifesize.com/)\.

   1. Choose **Account Settings** and **Device Settings**\.

   1. In the **Alexa for Business** section, enter the **Role ARN** and **External ID** from the CSV file you downloaded in step 1\. 

   1. Choose **Authenticate**\.

   1. Lifesize is now set as a conferencing provider in your Alexa for Business account\. If you are using another meeting service with Lifesize room systems, set up the conferencing provider\. For more information, see [Conferencing Providers](https://docs.aws.amazon.com/a4b/latest/ag/conference-providers.html)\.

1. Register your Lifesize room system device with Alexa for Business to enable Alexa on the device\.

   1. In the [Lifesize admin console](https://manage.lifesize.com/), choose **Room Systems**\.

   1. Select a room system that you want to register with Alexa for Business\.

   1. On the room system page, choose **Settings** and go to the Alexa for Business section\.

   1. Choose **Register**\.

   1. Select the **Room Profile** that you want to register the device to\.
**Note**  
If you don't see a profile or want to a new one, you can do so from your Alexa for Business account\. For more information, see [Manage room profiles](manage-profiles.md)\.

   1. Choose **Register**\. 

   1. Lifesize automatically creates a room within the profile and registers the Lifesize room system to that room in your Alexa for Business account\. The room has the same name as the Lifesize room system\.

**To remove Alexa for Business from your Lifesize room systems and account**

1. In the [Lifesize admin console](https://manage.lifesize.com/), choose **Account Settings** and **Device Settings**\. 

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Disconnect**, and from the confirmation screen, choose **Disconnect** again to confirm\.

1. Lifesize is now unauthenticated from your Alexa for Business account\. Any Lifesize room systems that were registered in your Alexa for Business account are automatically unregistered\.