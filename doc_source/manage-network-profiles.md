# Manage network profiles<a name="manage-network-profiles"></a>

To simplify the process of creating and managing network configurations, you can define network profiles\. Network profiles are associated with devices and consist of network configuration settings, including the SSID, network security type, network credentials, and description\. When you make a change to the network profile, the changes are applied to all shared devices associated with that profile\. If your shared devices are set up on a closed network, you can use network profiles for password rotation\. If your shared devices are set up on a WPA2 enterprise network, you can also use enterprise certificate rotation\. 

When you set up a device using the device setup tool, you must first select a network profile to associate devices to\. If the device was set up using **Import Devices**, you can associate the existing device to a network profile\. 

**To create a network profile**

1. Make sure that have you have the **AlexaForBusinessFullAccess** policy attached to your IAM user account\. For more information, see [Adding IAM Identity Permissions \(Console\)](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage-attach-detach.html#add-policies-console)\.

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Network profiles**, **Create network profile**\.

1. Fill in the following fields:
   + **Network SSID** – The name of the network SSID\. \(Required\)
   + **Description** – The description of your network profile\. This information helps you identify your network configuration if you have multiple network profiles\.
   + **Network security type** – The type of security that is used for your network\. From the drop\-down menu, choose from one of the following options:
     + **Open**
     + **WEP**
     + **WPA Personal**
     + **WPA2 Personal**
     + **WPA2 Enterprise**
   + For password\-based networks \(WEP, WPA Personal, and WPA2 Personal\): 
     + **Current password** – The current password of the network\. \(Required\) 
     + **Next password** – The next password of the network\. 
**Note**  
When you create a network profile for a password\-based Wi\-Fi network, Alexa for Business stores your passwords in AWS Secrets Manager and asynchronously transmits the network profile details to associated devices\. To rotate the wireless password for the network associated with your shared Echo devices, use and update the **Next password** field\.   
After the passwords are successfully transmitted to the device, the sync status for those devices changes to **Synced**\. You can then change the password of your network, and devices will continue to work with the new password\.

1. If you chose **WPA2 Enterprise**, complete the following steps\. Otherwise, skip these steps\.

   1. From the drop\-down menus, select the **EAP method** and **AWS certificate authority** that you created earlier, and choose **Next**\.
**Note**  
Certificate changes for the WPA2\_Enterprise network profile, including CA ARN and root certificate changes, are transmitted asynchronously to the devices\. 

   1. On the **Add root certificate** page to set up the Authentication Server Trust, provide the root certificate of your authentication server \(RADIUS\)\. This certificate is installed on your devices and used to trust your authentication server during EAP negotiation\. Select the certificate from a file on disk or paste it from your clipboard\. The certificate must be in PEM format\. When you're done, choose **Save**\.

1. Select devices to associate with the network profile \(optional\), and then choose **Create**\.

You can edit the room's name, description, and profile in **Network profile**\. 

**To edit a network profile**

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Network profiles** and choose the name of the network profile to edit\.

1. Edit any of the fields and choose **Save**\.

**To assign devices to a network profile**

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Network profiles** and choose the name of the network profile to associate devices to\.

1. Review the network profile details\. Choose **Associate a device**, and choose the devices to associate the network profile to\.

**To delete a network profile**

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Network profiles**\.

1. Select the check box next to the network profile to delete\.

1. Choose **Delete network profile**, **Delete**\.
**Note**  
You can delete a network profile only if no devices are associated to it\. 