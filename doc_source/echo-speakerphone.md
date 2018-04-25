# Use Echo Device as Speakerphone<a name="echo-speakerphone"></a>

**To use an Echo device as a speakerphone**

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