# Configure meeting room settings using Alexa for Business<a name="room-settings"></a>

Meeting room settings help you measure and improve your meeting room utilization\. You can enable end of meeting reminders, room utilization metrics, and intelligent room release\.

These settings are supported only when Alexa for Business is linked to an Office 365 or G Suite calendar system\.

**To configure meeting room settings**

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Room profiles**, **Create room profile**\.

1. Fill in the following fields under **Meeting room settings**:
   + **Room utilization metrics** – See how your meeting rooms are being used\. Learn how many meetings are booked in every room, and the amount of time that your rooms are reserved\. Enable **Intelligent room release**, described in the following item, to access additional metrics\. These metrics include attendance rate, freed up meeting room hours, and recovered meetings\. All metrics are available on the **Reports** tab in the console\. You can also schedule daily, weekly, or monthly delivery of room utilization metrics\. For information about how to schedule reports, see [Create a scheduled report](schedule-reports.md)\.
   + **Intelligent room release** – Release meeting room reservations when no one has checked into a reservation\. You can select a time frame within which a check\-in must occur\. Alexa notifies the room within a few minutes of release, and when the room is actually released\. If a device is offline, no release occurs\. Users are checked in when they interact with Alexa verbally, are in an active conference call on a device with Alexa built\-in, or if they say "Alexa, check in\." On Logitech Tap devices, users are also checked in if this setting is enabled and motion is detected\. When a room is released, the organizer is notified by an email from the address "no\-reply@a4b\.amazonaws\.com\."
   + **End of meeting reminder** – Alexa can remind the room when their meeting reservation is ending\. You can choose the timing of the reminder, and the reminder behavior\. Choose from the following audio and announcement options:
     + [Gentle chime](https://dbo6i7iv29x0s.cloudfront.net/audio/gentle_chime.wav)
     + [Knock](https://dbo6i7iv29x0s.cloudfront.net/audio/knock.wav)
     + [Alexa Announcement \#1: "Time check"](https://dbo6i7iv29x0s.cloudfront.net/audio/timecheck.wav)
     + [Alexa Announcement \#2: "5 minutes left" ](https://dbo6i7iv29x0s.cloudfront.net/audio/5minsleft.wav)
   + **Instant booking** – When an employee says "Alexa, join the meeting" and the room is free, Alexa automatically books the room for the selected duration\. 