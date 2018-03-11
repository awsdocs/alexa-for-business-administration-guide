# Use Cisco TelePresence with Alexa for Business<a name="using-cisco"></a>

You can connect Alexa for Business to your Cisco TelePresence systems to control meetings with your voice\.

To integrate Alexa with your Cisco TelePresence setup, download and install the Alexa for Business gateway\. For more information, see [Use the Alexa for Business Gateway](a4b-gateway.md)\. After you register, you can add the Cisco TelePresence endpoints to control using Alexa\. The Alexa for Business gateway is listening to an Amazon SQS queue for control commands\. When a user invokes the Alexa skill, a request is added to the queue and received by the Alexa for Business gateway\. The gateway processes the request and sends a control command to the Cisco TelePresence endpoint\.

You must meet the following requirements to proceed:

+ You have a Cisco TelePresence SX or DX system with  firmware version TC7\.3\.12 or CE8 or higher\.

+  HTTPS is enabled on your Cisco TelePresence system\.

+ You have Windows Server 2008 R2 or later, or any Linux server, to run the Alexa for Business gateway\.

+ Your locally deployed Alexa for Business gateway has access to the internet and local network access to control your Cisco TelePresence system\.

+ A conference provider has been added\.

**To use Cisco TelePresence with Alexa for Business**

1. Set up your provider in Alexa for Business\.

   1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

   1. Choose **Conference settings** and then choose the name of your default conferencing provider\.

   1. Enter the H323/SIP settings if they aren't filled in\. Alexa for Business uses these settings to create a dial\-in string when there is no scheduled meeting on the calendar\.

1. Enable the skill\.

   1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

   1. Choose** Conference settings** and **Alexa for Cisco TelePresence** in the list of conference equipment\.

   1. Choose **Enable** to enable the skill\.

   1. You receive a prompt to link an account\. Sign in or create an Amazon\.com account \(for example, marymajor@example\.com\)\.

   1. Choose **Skills**, **Enabled skills**, and then select the skill\.

   1. Choose **Assign to skill group** and choose the skill group associated with the rooms where you want to make the skill available\.

1. Install the Alexa for Business gateway\. For more information, see [Use the Alexa for Business Gateway](a4b-gateway.md)\. 

1. Add your Cisco TelePresence system to Alexa for Business and add it to a room\.

   1. Choose **Endpoint**, **Add endpoint**\.

   1. Specify the **Cisco TelePresence** system name\.

   1. Enter a friendly name, which can be used by the customer to identify the device\. Enter an optional description\.

   1. \(Optional\) Enter a description\.

   1. Choose the **Cisco TelePresence** model\.

   1. Specify the IP address or hostname of your Cisco TelePresence endpoint\.

   1. Choose the Alexa for Business room where the Cisco TelePresence endpoint is located\.

   1. Choose **Add**\.

   1. Choose **Rooms** and the name of the room where you just assigned the Cisco TelePresence endpoint\.

   1. Choose **Discover devices** to have the endpoint available in your room\.

   1. Test the integration by saying “Alexa, start my meeting” and speak out the meeting ID and PIN for your meeting when prompted\. 

**To add a Cisco TelePresence endpoint**

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Conferencing settings**, **Alexa for Cisco TelePresence**\.

1. In the endpoint section, choose **Add endpoint**\. For **System name**, enter **Cisco TelePresence**\.

1. Enter a friendly name, which can be used by the customer to identify the device\. Enter an optional description\.

1. Choose **Cisco TelePresence model** and specify the IP address or hostname of your Cisco TelePresence endpoint\.

1. Choose the Alexa for Business room where the Cisco TelePresence endpoint is located and choose **Add**\.

1. Choose **Rooms** and the name of the room where you just assigned the Cisco TelePresence endpoint\.

1. To have the endpoint available in your room, choose **Discover devices**\.

You can now use Alexa to control your Cisco TelePresence endpoint using voice\.

**To remove an endpoint**

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Conferencing settings**, **Alexa for Cisco TelePresence**\.

1. Go to the endpoint section and select the check box next to the device to deregister\. 

1. Choose **Remove**\.