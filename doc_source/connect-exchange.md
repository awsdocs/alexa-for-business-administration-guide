# Set up Microsoft Exchange Access for Users<a name="connect-exchange"></a>

You can link Alexa for Business to your Microsoft Exchange server\. This enables enrolled users to ask Alexa about their scheduled events or add new events to their Microsoft Exchange calendar\.

To give enrolled users access to their Microsoft Exchange calendar, set up a service account on your Microsoft Exchange server to access the users' calendars\. After the service account is set up, users can link Alexa to their Microsoft Exchange using the Alexa app\.

If you already set up a service account to access your room calendars, skip to step 3 and give the service account permissions to your users' calendars\.

Before your proceed, confirm that you meet the following requirements:

+ You have an administrator account within your Microsoft Exchange server\.

+ Microsoft Exchange is version 2013 or higher\.

+ You have a valid Exchange Web Services \(EWS\) endpoint with a valid digital certificate purchased from a trusted public certificate authority \(CA\)\.

+ Basic authentication is enabled on both your Microsoft Exchange server and Autodiscover service\.

**Create a service account with access to the calendars in your organization\.**

1. Open the Exchange Management Shell\.

1. Run the following command to create the service account\.

   ```
   New-Mailbox -UserPrincipalName alexaforbusiness@your_domain
                                   -Alias Alexa for Business -Name alexaforbusiness -OrganizationalUnit
                                   Users -FirstName Alexa -LastName Service Account -DisplayName "Alexa
                                   for Business Service Account"
   ```
**Note**  
Make sure that "your\_domain" is the domain of your organization\. You are prompted to enter a password\.

The service account must have permissions to access the calendars in your organization\. You can enable service account access to the calendars in your organization by using one of the following two methods:

+ Set up impersonation, which enables the service account to impersonate a given account so that it can perform all operations using the permissions associated with the given account:

+ Add the service account as full access and send as permissions for each of your user mailboxes\. 

**To set up impersonation**

1. Open the Exchange Management Shell and run the following command:

   New\-ManagementRoleAssignment –name:impersonationAssignmentName –Role:ApplicationImpersonation –User: alexaforbusiness 

1. To limit the service account, define the scope\. For example, to only give the service account permissions to the room mailboxes in the organization, run the following command in Exchange Management Shell:

   New\-ManagementScope \-Name "UserMailboxes" \-RecipientRestrictionFilter \{RecipientTypeDetails \-eq "UserMailbox"\}

1. To apply permissions to the service account, run the following command:

   New\-ManagementRoleAssignment –Name "ResourceImpersonation" –Role ApplicationImpersonation –User alexaforbusiness –CustomRecipientWriteScope "UserMailboxes"

**To add the service account as full access**

+ Run the following command to give the service account access to all user mailboxes:

  ```
  $users = Get-Mailbox -ResultSize unlimited -Filter
                                          (RecipientTypeDetails -eq 'UserMailbox' ) | Select
                                          -ExpandProperty Alias Foreach ($user in $users) {
                                          Add-MailboxFolderPermission $user":\Calendar" -user
                                          alexaforbusiness -accessrights Editor Add-ADPermission $user –User
                                          alexaforbusiness -Extendedrights "Send As" }
  ```

**To link the service account to Alexa for Business**

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Calendar**, **Microsoft Exchange**\.

1. Enter the User Principal Name \(UPN\) of your service account and service account password\.

1. Enter the URL of your EWS endpoint\. The default URL for EWS is usually in the following format: https://mail\.domain\.com/EWS/Exchange\.asmx\.

1. Select the access method that you have set up and choose **Link account**\.

**To test integration to access the calendar of an enrolled user**

1. Open the Alexa app as an enrolled user\.

1. Choose **Settings**, **Calendar**\.

1. Choose **Microsoft Exchange** and complete the required steps\.

Alexa can now read back the upcoming events on the calendar\. 