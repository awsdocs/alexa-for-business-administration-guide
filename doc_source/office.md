# Link Alexa for Business to Office 365<a name="office"></a>

By default, linking Alexa for Business to Office 365 gives the Alexa for Business client app read access to your organization’s calendars\. Granting full read permissions enables Alexa for Business to default to the organizer’s calendar when the room calendar’s invitation is insufficient to automatically join a meeting\. If you want to grant access to specific room calendars, see [Link Alexa for Business to Office 365 \(Limit Access Option\)](office-limit.md)\.

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Calendar**, **Office 365**\.

1. Choose **Link account** and sign in with the Office 365 account that belongs to the Global Administrators group\.

1. Give consent that Alexa for Business has read access to the calendars in your Office 365 organization\.

1. Associate the email address of your resource mailboxes in Office 365 to your Alexa for Business rooms\. 

   1. In the Alexa for Business console, choose **Rooms** and choose the room to which to add the email address\.

   1. Choose **Edit** and enter the email address of your resource mailbox to associate to the Alexa for Business room\. 

   1. Choose **Save**\.

1. Test the calendar integration\. 

   1. Create a new meeting invite in your Microsoft Outlook client\.

   1. Add the room as the resource, add meeting dial\-in information to your meeting invite, and send the invite to book the room\. 

   1. Say “Alexa, start my meeting” to the Echo device assigned to the room\.

Your Echo device automatically dials into your meeting without prompting you for a meeting ID\. 