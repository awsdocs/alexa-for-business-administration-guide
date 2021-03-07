# Security and privacy frequently asked questions for the Alexa for Business Windows Client \(Zoom Room Edition\)<a name="zoom-security"></a>

The following is a list of frequently asked security questions about using the Alexa for Business Windows Client \(Zoom Room Edition\): 
+ ***Does Alexa listen to everything that is being said?***

  No\. The Alexa cloud only receives audio after the wake word is said or the action button is pressed\. Until then, the Alexa client waits to hear the wake word unless muted\. Alexa turns off the audio stream after enough audio is received to run the intended command\.
+ ***How do I know when audio is streaming to the Alexa cloud?***

  A tone will play to indicate that the wake word was detected\. In addition, a blue bar will appear on the video screen\. This blue bar indicates that Alexa is engaged in receiving or sending audio\.
+ ***Can I make sure that no data streams to the Alexa cloud?***

  Yes\. Use the on\-screen Alexa mute button to turn off the wake word detection\. After you do that, no audio will be streamed to the Alexa cloud\.
+ ***Does the Alexa for Business Windows Client \(Zoom Room Edition\) retain audio data?***

  No\. While looking for the wake word, the Alexa for Business Windows Client \(Zoom Room Edition\) puts the audio stream into a small audio buffer, which is continuously overwritten by new, incoming audio\.
+ ***Does the Alexa system retain all the audio that it receives?***

  Retention of utterance history is under the control of the local system administrators and of the users\. System administrators can delete history on a regular basis, or manually clear data for a given device\. A user can say "Alexa, forget what I just said" or "Alexa, forget what I said today" to clear recent history\.
+ ***Can anyone at my company listen to what was said to Alexa?***

  No\. Administrators can delete recordings, but they can't listen to them, and there is no administrator access to review any recordings made from the Alexa for Business Windows Client \(Zoom Room Edition\)\. In addition, manual review by Amazon is turned off by default for the Alexa for Business Windows Client \(Zoom Room Edition\)\. As a result, recordings will not be reviewed by humans at Amazon for the purpose of improving the Alexa system\.
+ ***Does Alexa retain the meeting ID and password of Zoom meetings that I join?***

  If a user joins a scheduled meeting, no meeting ID or password is captured or retained\. If a user joins an ad hoc meeting and tells Alexa the meeting ID and password to join, both are retained\. However, system administrators can automatically delete voice recordings \(including Meeting IDs and passwords\) on a regular basis \(for example, every 24 hours\)\. They can also manually clear data for any given device\. In addition, manual review by Amazon is turned off by default for the Alexa for Business Windows Client \(Zoom Room Edition\)\. As a result, recordings will not be reviewed by humans at Amazon for the purpose of improving the Alexa system\.