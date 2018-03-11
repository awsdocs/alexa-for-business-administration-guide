# Link Alexa for Business to Microsoft Exchange<a name="exchange"></a>

**To link Alexa for Business to Microsoft Exchange**

1. Before you proceed, confirm that you meet the following requirements:

   + You have an administrator account within your Microsoft Exchange server\.

   + Microsoft Exchange is version 2010 SP1 or higher\.

   + You have a valid Exchange Web Services \(EWS\) endpoint\.

   + You have basic authentication enabled on your Exchange Web Servers \(EWS\) endpoint\.

1. Verify that basic authentication is enabled:

   1. Open Microsoft Exchange Management Shell\.

   1. Type **Get\-WebServicesVirtualDirectory | fl**\.

   1. Verify that the parameter** BasicAuthentication** is set to **True**\.

1. If basic authentication isn't enabled, run the following command to enable it:

   Set\-WebServicesVirtualDirectory \-Identity "Contoso\\EWS\(Default Web Site\)" \-BasicAuthentication $true
**Note**  
Contoso\\EWS\(Default Web Site\) is the identity of the Microsoft Exchange Web Services virtual directory\.

1. Create a service account with access to the calendars in your organization\.

   1. Open the Exchange Management Shell\.

   1. Run the following command to create the service account\.

      New\-Mailbox \-UserPrincipalName alexaforbusiness@your\_domain \-Alias Alexa for Business \-Name alexaforbusiness \-OrganizationalUnit Users \-FirstName Alexa \-LastName Service Account \-DisplayName "Alexa for Business Service Account"
**Note**  
Make sure that "your\_domain" is the domain of your organization\. You are prompted to enter a password\.

1. To look up meeting dial\-in information from your resource mailboxes, configure them to include descriptions:

   1. Open the Exchange Management Shell\. 

   1. Run the following command to keep the descriptions in the meeting invites of your resource mailboxes:

      Get\-Mailbox \-ResultSize unlimited \-Filter \{\(RecipientTypeDetails \-eq 'RoomMailbox' \)\} | Set\-CalendarProcessing \-DeleteComments $FALSE

1. Set up permissions\. The service account must have permissions to access the calendars in your organization\. You can enable service account access to the calendars in your organization by using one of the following two methods:

   + Method 1: Set up impersonation, which enables the service account to impersonate a given account so that it can perform all operations using the permission associated with the given account:

     1. Open the Exchange Management Shell and run the following command:

        New\-ManagementRoleAssignment –name:impersonationAssignmentName –Role:ApplicationImpersonation –User: alexaforbusiness 

   + Method 2: Add the service account as delegate for each of your room mailboxes\. 

     1. Run the following command to give the service account access to all room mailboxes:

        Get\-Mailbox \-ResultSize unlimited \-Filter \(RecipientTypeDetails \-eq 'RoomMailbox' \) | Add\-MailboxPermission \-User alexaforbusiness \-AccessRights ReadPermission

1. Link the service account to Alexa for Business\.

   1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

   1. Choose **Calendar**, **Microsoft Exchange**\.

   1. Enter the User Principal Name \(UPN\) of your service account\.

   1. Enter the service account password\.

   1. Enter the URL of your EWS endpoint\. The default URL for EWS is usually in the following format: https://mail\.domain\.com/EWS/Exchange\.asmx\.

   1. Select the access method you have set up\.

   1. Choose **Link account** to complete the setup\.

1. Associate the email address of your resource mailboxes in Microsoft Exchange to your Alexa for Business rooms\.

   1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

   1. Choose **Rooms** and choose the room to which to add the email address\.

   1. Choose **Edit**\.

   1. Enter the email address of your resource mailbox that you want to associate to the Alexa for Business room\.

   1. Choose **Save**\.

1. Test the integration\.

   1. Create a new meeting invite in your Microsoft Outlook client\.

   1. Add the room as the resource\.

   1. Add meeting dial\-in information to your meeting invite\.

   1. Send the invite to book the room\.

   1. Say “Alexa, start my meeting” to the Echo device assigned to the room\.

   1. Your Echo device prompts you to join the scheduled meeting without asking you for the meeting ID\.

If you have any issues linking Alexa for Business to Microsoft Exchange, try these troubleshooting tips:

+ If account linking fails in the Alexa app, verify that the email address you invited the user with matches the email address in your Microsoft Exchange server\. Also, make sure that basic authentication is enabled for your Exchange Web Services \(EWS\) endpoint\.

+ To test the connectivity to your Microsoft Exchange server, use the [Microsoft Remote Connectivity Tester](https://testconnectivity.microsoft.com)\. To test your setup, choose **Service Account Access** under the **Microsoft Exchange Web Services Connectivity Tests**\. Use the email address of the user that failed to link their account as the target mailbox email address and impersonated user\.

+ If setting up the Microsoft Exchange account fails in Alexa for Business and you see the error message "The calendar account could not be linked\. If the issue persists, contact AWS Support\. Invalid parameter provided”, validate that your Exchange Web Services \(EWS\) endpoint is valid and remotely accessible\. 