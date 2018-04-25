# Link Alexa for Business to Office 365 \(Limit Access Option\)<a name="office-limit"></a>

By default, linking Alexa for Business to Office 365 gives the Alexa for Business client app read access to your organization’s calendars\. Granting full read permissions enables Alexa for Business to default to the organizer’s calendar when the room calendar’s invitation is insufficient to automatically join a meeting\. If you want to grant access to specific room calendars, follow these steps\.

1. Connect to Exchange Online PowerShell\. For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)\. 

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