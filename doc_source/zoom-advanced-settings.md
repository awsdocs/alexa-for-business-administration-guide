# Configure advanced settings<a name="zoom-advanced-settings"></a>

After you enable Alexa for Business, you can turn on advanced features in the Alexa for Business console\. You can enable room booking features \(“Alexa, find a room”\), private skills \(“Alexa, what’s our guest wireless information?”\), end of meeting reminders, and general skills\.

**To enable advanced Alexa for Business settings**

1. Before you can use the Alexa for Business console, make sure that you meet the [Prerequisites for Alexa for Business](setting-up.md)\.

1. [Link Alexa for Business to your calendar system](manage-calendaring.md) to enable the following utterances:
   + “Alexa is this room free?” and “Alexa, is this room booked at noon?”
   + “Alexa, who booked this room?”
   + “Alexa, book the room” and “Alexa, reserve the room until 10 am”
   + “Alexa, extend the meeting” and “Alexa, extend the meeting for half an hour”
   + “Alexa, find a room,” “Alexa, find a room for an hour,” and “Alexa, find a room at noon”
**Note**  
Every room is assigned to a *room profile*, which is a group of settings\. When you ask to find an available room, Alexa will only search for Zoom Rooms in the same profile\. Make sure that rooms in close proximity to one another are in the same profile for helpful booking\. To configure this, see [Manage room profiles](manage-profiles.md)\.  
For example, room profile A includes rooms 1, 2, and 3, and room profile B includes rooms 4, 5, and 6\. If a user walks into room 1 and asks for an available room, Alexa will respond with rooms 1, 2, or 3, depending on availability\.

1. To turn on end of meeting reminders and instant booking, follow these steps:

   1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

   1. Choose **Room profiles**, **Create room profile**\.

   1. In **Meeting room settings**, choose from the following settings:
      + **End of meeting reminder** – Alexa can remind the room when their meeting reservation is ending\. You can choose the timing of the reminder and the reminder behavior\. Choose from the following audio and announcement options:
        + [Gentle chime](https://dbo6i7iv29x0s.cloudfront.net/audio/gentle_chime.wav)
        + [Knock](https://dbo6i7iv29x0s.cloudfront.net/audio/knock.wav)
        + [Alexa Announcement \#1: “Time check”](https://dbo6i7iv29x0s.cloudfront.net/audio/timecheck.wav)
        + [Alexa Announcement \#2: “5 minutes left” ](https://dbo6i7iv29x0s.cloudfront.net/audio/5minsleft.wav)
      + **Instant booking** – When an individual says “Alexa, join the meeting” and the room is free, Alexa can automatically book the room for the selected duration\.

1. To set up private skills, see [Private skills](private-skills.md)\.

1. To set up general skills, see [Manage skills](manage-skills.md)\.