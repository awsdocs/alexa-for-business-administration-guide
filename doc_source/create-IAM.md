# Create IAM users and policies<a name="create-IAM"></a>

The Alexa for Business console requires a user name and password so that the service can determine whether you have permission to access its resources\. We recommend that you avoid using AWS account credentials for general access because those credentials cannot be revoked or limited in any way\. For more information, see [AWS security credentials](https://docs.aws.amazon.com/general/latest/gr/aws-security-credentials.html) in the *AWS General Reference*\.

Instead, use AWS Identity and Access Management \(IAM\) to create an IAM user and add the user to an IAM group with administrative permissions\. You can then access the Alexa for Business console using the credentials for the IAM user\. If you signed up for AWS but have not created an IAM user for yourself, you can create one using the IAM console\. For more information, see [Creating an IAM user in your AWS account](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html) in the *IAM User Guide*\.

By default, IAM users don't have permissions to manage Alexa for Business resources\. You must use a customer managed policy that explicitly grants IAM users those permissions, and attach the policy to the specific IAM users or groups that require those permissions\. For more information, see the following topics in the *IAM User Guide*:
+ [Managed policies and inline policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-vs-inline.html)
+ [Access management](https://docs.aws.amazon.com/IAM/latest/UserGuide/access.html)

