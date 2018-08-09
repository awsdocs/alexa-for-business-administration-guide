# Link Alexa for Business to Office 365 \(Limit Access Option\)<a name="office-limit"></a>

By default, linking Alexa for Business to Office 365 gives the Alexa for Business client app read access to your organization’s calendars\. Granting full read permissions enables Alexa for Business to default to the organizer’s calendar when the room calendar’s invitation is insufficient to automatically join a meeting\. If you want to grant access to specific room calendars, follow these steps\.

1. Create a service account for Alexa for Business in your Office 365 tenant:

   1. Sign into Office 365 as an administrator\.

   1. Add a user in your Office 365 account that will use a service account\. For more information, see [Add users individually or in bulk to Office 365](https://support.office.com/en-us/article/add-users-individually-or-in-bulk-to-office-365-admin-help-1970f7d6-03b5-442f-b385-5880b9c256ec?CorrelationId=8d4aa47b-49a9-48ad-87fc-dcd9a595f28c&ui=en-US&rs=en-US&ad=US)\.

      For example, if your domain is "mycompany\.com" and you add a user with the user name of "alexaforbusiness," the email address is "alexaforbusiness@mycompany\.com"\.

1. Open PowerShell and connect to Exchange Online\. For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)\. 

1. Run the following PowerShell command to create a service account with access to the calendars in your organization:

   `New-Mailbox -UserPrincipalName alexaforbusiness@your_domain -Alias Alexa for Business -Name alexaforbusiness -OrganizationalUnit Users -FirstName Alexa -LastName Service Account -DisplayName "Alexa for Business Service Account"`
**Note**  
Make sure that "your\_domain" is the domain of your organization, and enter your password when prompted\.

1. To look up meeting dial\-in information from your resource mailboxes, configure them to include descriptions\. Run one of the following commands to keep the descriptions in the meeting invites of your resource mailboxes:

   For a single room mailbox:

   `Set-CalendarProcessing <room name> -DeleteComments $FALSE` 

   For all room mailboxes:

   `Get-Mailbox -ResultSize unlimited -RecipientTypeDetails 'RoomMailbox' | Set-CalendarProcessing -DeleteComments $FALSE`

1. Run one of the following commands to give the service account permissions to access the room calendars in your organization:

   For a single room mailbox:

   `Add-MailboxFolderPermission <room name>:\Calendar -User alexaforbusiness -AccessRights ReadItems` 

   For all room mailboxes:

   `Get-Mailbox -ResultSize unlimited -RecipientTypeDetails 'RoomMailbox' | ForEach-Object {Add-MailboxFolderPermission $_":\calendar" -user alexaforbusiness -AccessRights ReadItems}`

1. To link the service account to Alexa for Business, follow these steps:

   1. In the Alexa for Business console, choose **Calendar**, **Microsoft Exchange**\.

   1. Enter the user principal name \(UPN\) of the service account you created earlier, service account password, and URL of the Office 365 EWS endpoint \(https://outlook\.office365\.com/EWS/Exchange\.asmx\)\.

   1. For **Access method**, select **Delegation**\.

   1. Choose **Link account**\.

Now you can associate the email address of your resource mailboxes with your rooms in Alexa for Business\.