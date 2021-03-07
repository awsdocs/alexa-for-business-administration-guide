# Create usage reports for Alexa for Business<a name="creating-reports"></a>

You can see how Alexa for Business helps your organization by creating usage reports\.

Usage reports consist of \.csv files that you can view in BI tools\. You can use them for further analysis by using ETL processes\. A visual HTML report is generated alongside the \.csv files\. It gives you a comprehensive view of Alexa for Business use in your organization\. You can create a report to deliver immediately to your S3 bucket, or create a scheduled report that gets delivered automatically to your S3 bucket daily or weekly\. The \.csv files contain 1\-day or 7\-day aggregate metrics based on your selection\. The HTML report shows a summary of the last 30 days of use\.

**Metrics**

Usage reports include the following metrics:
+ Invocations on shared devices
+ Meetings joined using Alexa
+ Private skill invocations
+ Active enrolled users
+ Alexa invocations on shared devices
+ Meetings joined
+ Private skill invocations
+ Daily active enrolled users of Alexa for Business
+ Meetings joined on shared devices 
+ Meetings auto\-joined and joined by PIN
+ Total utilization by room name on shared devices 
+ Meetings joined by room name on shared devices
+ Private skill invocations on shared devices
+ Top five invocation types on shared devices
+ Top 25 invocation types on shared devices
+ Total number of private skill invocations
+ 30 day room utilization report \(for more information, see [View room utilization metrics](room-metrics.md)\)

**Topics**
+ [Usage report prerequisites](report-prerequisites.md)
+ [Create a report](create-report.md)
+ [Create a scheduled report](schedule-reports.md)