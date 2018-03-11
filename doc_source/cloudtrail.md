# Logging Alexa for Business Administration Calls with AWS CloudTrail<a name="cloudtrail"></a>

Alexa for Business is integrated with CloudTrail\. CloudTrail is a service that captures API calls made by or on behalf of Alexa for Business in your AWS account and delivers the log files to an Amazon S3 bucket that you specify\. CloudTrail captures all API calls from the Alexa for Business console\. Using the information collected by CloudTrail, you can determine which requests were made, the source IP address for the request, who made the request, and when it was made\. For more information, including how to configure and enable CloudTrail, see the [AWS CloudTrail User Guide](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)\.

When CloudTrail logging is enabled in your AWS account, API calls made from Alexa for Business on your behalf are tracked in log files\. These records are written together with other AWS service records in a log file\. CloudTrail determines when to create and write to a new file based on time period and file size\.

You can store your log files in your bucket for as long as you want, or you can define Amazon S3 lifecycle rules to archive or delete log files automatically\. By default, your log files are encrypted using Amazon S3 server\-side encryption \(SSE\)\. To take quick action upon log file delivery, you can choose to have CloudTrail publish Amazon SNS notifications when new log files are delivered\. For more information, see [Configuring Amazon SNS Notifications for CloudTrail](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/configure-sns-notifications-for-cloudtrail.html)\. 

CloudTrail log files can contain one or more log entries, with each entry comprised of multiple JSON\-formatted events\. A log entry represents a single request and contains information about the action taken, who generated the request, where they were when they made the request, system information, and information that will vary depending on the type of request\. Every log entry also contains information about who generated the request\. The user identity information in the log helps you determine whether the request was made with root or IAM user credentials, with temporary security credentials for a role or federated user, or by another AWS service\. For more information, see the **userIdentity** field in the [CloudTrail Log Event Reference](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-event-reference.html)\.

Log entries are not in any particular order and are not an ordered stack trace of the public API calls\. Entries for Alexa for Business are identified by the **a4b\.amazonaws\.com** event source\. Sensitive information, such as passwords, authentication tokens, file comments, and file contents, are redacted in log entries\.

The following is an example of a CloudTrail log entry for Alexa for Business:

```
{
  "Records": [{
    "eventVersion": "1.05",
    "userIdentity": {
      "type": "IAMUser",
      "principalId": "EX_PRINCIPAL_ID",
      "arn": "arn:aws:iam::123456789012:user/Alice",
      "accountId": "123456789012",
      "accessKeyId": "EXAMPLE_KEY_ID",
      "userName": "Alice"
    },
    "eventTime": "2017-11-13T10:00:02Z",
    "eventSource": "a4b.amazonaws.com",
    "eventName": "CreateRoom",
    "awsRegion": "us-east-1",
    "sourceIPAddress": "192.2.0.1",
    "userAgent": "AWS Internal",
    "requestParameters": null,
    "responseElements": {
      "roomArn": "arn:aws:a4b:us-east-1:123456789012:room/8eed09c4eae340d2ba08b8c6c3e40970/66afda686e75c5b62fceaf60ac00e7a6"
    },
    "requestID": "6a875d42-c859-11e7-93bc-f944dc16ba6b",
    "eventID": "2b045b94-82d9-407d-aff3-6c308b40fecb",
    "resources": [{
      "ARN": "arn:aws:a4b:us-east-1:123456789012:profile/8eed09c4eae340d2ba08b8c6c3e40970/00491b672c651240de09540d2072f660",
      "accountId": "123456789012",
      "type": "AWS::A4B::Profile"
    }, {
      "ARN": "arn:aws:a4b:us-east-1:123456789012:room/8eed09c4eae340d2ba08b8c6c3e40970/66afda686e75c5b62fceaf60ac00e7a6",
      "accountId": "123456789012",
      "type": "AWS::A4B::Room"
	}],
    "eventType": "AwsApiCall",
    "recipientAccountId": "123456789012"
    }
  ]
```