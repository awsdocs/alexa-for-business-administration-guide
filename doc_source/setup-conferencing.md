# Set up Alexa Conferencing<a name="setup-conferencing"></a>

Alexa for Business enables you to dial into meetings by just using your voice\. You can use Alexa to connect to meetings by controlling existing video conferencing equipment or by using the Echo device as a speaker phone\. Alexa for Business offers Alexa skills for the most common video conferencing equipment\.

When Alexa hears a user request “Alexa, join my meeting,” the request is sent to the Alexa for Business conferencing service\. When the meeting room has a supported video conferencing system, the request is sent to the third\-party Alexa skill\. The skill communicates with the video conferencing system, looks up if there is a scheduled meeting on the calendar, and prompts the user for confirmation to join this meeting\. If there is no scheduled meeting, Alexa prompts the user for the meeting ID and optionally the PIN to join their meeting\. The skill initiates a video conferencing call from the video conferencing system to your conferencing provider\.

When the room doesn’t contain a supported video conferencing setup, Alexa searches for a scheduled meeting on the calendar and prompts the user for a confirmation to join the meeting\. If there is no scheduled meeting, Alexa prompts the user for the meeting ID and optionally the PIN to join the meeting, and makes a PSTN call to your conferencing provider\.

Alexa for Business can join scheduled meetings of the following conferencing providers:

+ Amazon Chime

+ BlueJeans

+ Zoom

+ RingCentral Meetings

+ Cisco WebEx

+ Skype for Business

**To configure Alexa for Business to join meetings with an Echo device**

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Room profiles**, choose the name of the room profile associated with your meeting rooms, and enable **Outbound calling**\.

1. Choose **Conferencing**, **Add provider**\.

1. Choose one of the available conferencing providers, which automatically fills in the **Provider** pane\.
**Note**  
If the conference provider used by your organization is not available, choose **Custom conferencing provider**\.

1. Review the following settings and edit them as necessary:

   + **Meeting settings** – Specify whether a meeting PIN is required to join the meeting\. \(Required\)

   + **PSTN dial\-in number** – Specify the phone number of your conferencing provider\. This must be a US phone number\.

   + **PSTN dial\-in delays** – Specify the delays before the meeting ID and PIN are sent using DTMF\.

1. Choose **Add**\.

1. \(Optional\) To join scheduled meetings, link your calendar to Alexa for Business\. For more information, see [Link Alexa for Business to Your Calendar System](manage-calendaring.md)\.

You can now say “Alexa, join my meeting” and Alexa prompts you to join the scheduled meeting or to provide the ID of the meeting to join\.