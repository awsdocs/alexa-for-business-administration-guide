# Prerequisites<a name="zoom-account"></a>

Before you can begin, confirm that you have the following prerequisites:
+ The following devices are supported:
  + Zoom Rooms: Windows IoT OS
  + Zoom Rooms Controller: Logitech Tap, Lenovo ThinkSmart Hub touch display
  + Camera/Speaker/Microphone: Logitech Meetup, Logitech, Rally, Lenovo ThinkSmart Hub internal microphone/speaker
**Note**  
If you don’t have the supported devices described earlier, you can deploy an Echo device in your rooms to use Alexa for Business to control your Zoom Rooms\. For more information, see [Use Echo devices to control Zoom Rooms](use-zoom.md)\.
+ A Zoom Rooms admin account that has a Business, Education, or Enterprise plan\.
**Note**  
Alexa for Business supports one Zoom organization connected to one AWS organization\. If you try to connect multiple Zoom organizations to one AWS organization, or multiple AWS organizations to one Zoom organization, previously provisioned rooms will be deactivated\.
+ An AWS account\. For more information, see [Sign up for AWS](console_signup.md)\.
**Note**  
Your AWS account is automatically signed up for all services in AWS\. You are charged only for the services that you use\.
+ A Microsoft 365 service account that has permissions to read and write to your room calendars\.
+ AWS Identity and Access Management \(IAM\) user account access to Alexa for Business\. For information about adding an IAM user to your AWS account, see [Create IAM users and policies](create-IAM.md)\. To grant your IAM account access to Alexa for Business, use the following steps to attach the following `AlexaforBusinessFullAccess` policy to your IAM user account:

  1. Open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

  1. Choose **Users**, enter your user name in the search box, and then select it from the list\.

  1. Choose **Add permissions**, **Attach existing policies directly**\.

  1. In the search box, enter **AlexaforBusinessFullAccess** and select it from the list\.

  1. Choose **Next: Review**, **Add permissions**\.