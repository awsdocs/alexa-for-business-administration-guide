# How Alexa for Business works with IAM<a name="security_iam_service-with-iam"></a>

Before you use IAM to manage access to Alexa for Business, you should understand what IAM features are available to use with Alexa for Business\. To get a high\-level view of how Alexa for Business and other AWS services work with IAM, see [AWS Services That Work with IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_aws-services-that-work-with-iam.html) in the *IAM User Guide*\.

**Topics**
+ [Alexa for Business identity\-based policies](#security_iam_service-with-iam-id-based-policies)
+ [Alexa for Business resource\-based policies](#security_iam_service-with-iam-resource-based-policies)
+ [Access control lists \(ACLs\)](#security_iam_service-with-iam-acls)
+ [Authorization based on Alexa for Business tags](#security_iam_service-with-iam-tags)
+ [Alexa for Business IAM roles](#security_iam_service-with-iam-roles)

## Alexa for Business identity\-based policies<a name="security_iam_service-with-iam-id-based-policies"></a>

With IAM identity\-based policies, you can specify allowed or denied actions and resources, and also the conditions under which actions are allowed or denied\. Alexa for Business supports specific actions, resources, and condition keys\. For more information about all of the elements that you use in a JSON policy, see [IAM JSON Policy Elements Reference](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements.html) in the *IAM User Guide*\.

### Actions<a name="security_iam_service-with-iam-id-based-policies-actions"></a>

Administrators can use AWS JSON policies to specify who has access to what\. That is, which **principal** can perform **actions** on what **resources**, and under what **conditions**\.

The `Action` element of a JSON policy describes the actions that you can use to allow or deny access in a policy\. Policy actions usually have the same name as the associated AWS API operation\. There are some exceptions, such as *permission\-only actions* that don't have a matching API operation\. There are also some operations that require multiple actions in a policy\. These additional actions are called *dependent actions*\.

Include actions in a policy to grant permissions to perform the associated operation\.

Policy actions in Alexa for Business use the following prefix before the action: `a4b:`\. For example, to grant someone permission to run an Amazon EC2 instance with the Amazon EC2 `RunInstances` API operation, you include the `ec2:RunInstances` action in their policy\. Policy statements must include either an `Action` or `NotAction` element\. Alexa for Business defines its own set of actions that describe tasks that you can perform with this service\.

To specify multiple actions in a single statement, separate them with commas as follows:

```
"Action": [
      "ec2:action1",
      "ec2:action2"
```

You can specify multiple actions using wildcards \(\*\)\. For example, to specify all actions that begin with the word `Describe`, include the following action:

```
"Action": "ec2:Describe*"
```



To see a list of Alexa for Business actions, see [Actions Defined by Alexa for Business](https://docs.aws.amazon.com/IAM/latest/UserGuide/list_alexaforbusiness.html#alexaforbusiness-actions-as-permissions) in the *IAM User Guide*\.

### Resources<a name="security_iam_service-with-iam-id-based-policies-resources"></a>

Administrators can use AWS JSON policies to specify who has access to what\. That is, which **principal** can perform **actions** on what **resources**, and under what **conditions**\.

The `Resource` JSON policy element specifies the object or objects to which the action applies\. Statements must include either a `Resource` or a `NotResource` element\. As a best practice, specify a resource using its [Amazon Resource Name \(ARN\)](https://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html)\. You can do this for actions that support a specific resource type, known as *resource\-level permissions*\.

For actions that don't support resource\-level permissions, such as listing operations, use a wildcard \(\*\) to indicate that the statement applies to all resources\.

```
"Resource": "*"
```



The Amazon EC2 instance resource has the following ARN:

```
arn:${Partition}:ec2:${Region}:${Account}:instance/${InstanceId}
```

For more information about the format of ARNs, see [Amazon Resource Names \(ARNs\)](https://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html)\.

For example, to specify the `i-1234567890abcdef0` instance in your statement, use the following ARN:

```
"Resource": "arn:aws:ec2:us-east-1:123456789012:instance/i-1234567890abcdef0"
```

To specify all instances that belong to a specific account, use the wildcard \(\*\):

```
"Resource": "arn:aws:ec2:us-east-1:123456789012:instance/*"
```

Some Alexa for Business actions, such as those for creating resources, cannot be performed on a specific resource\. In those cases, you must use the wildcard \(\*\)\.

```
"Resource": "*"
```

Many Amazon EC2 API actions involve multiple resources\. For example, `AttachVolume` attaches an Amazon EBS volume to an instance, so an IAM user must have permissions to use the volume and the instance\. To specify multiple resources in a single statement, separate the ARNs with commas\. 

```
"Resource": [
      "resource1",
      "resource2"
```

To see a list of Alexa for Business resource types and their ARNs, see [Resources Defined by Alexa for Business](https://docs.aws.amazon.com/IAM/latest/UserGuide/list_alexaforbusiness.html#alexaforbusiness-resources-for-iam-policies) in the *IAM User Guide*\. To learn with which actions you can specify the ARN of each resource, see [Actions Defined by Alexa for Business](https://docs.aws.amazon.com/IAM/latest/UserGuide/list_alexaforbusiness.html#alexaforbusiness-actions-as-permissions)\.

### Condition keys<a name="security_iam_service-with-iam-id-based-policies-conditionkeys"></a>

Alexa for Business does not support any global condition keys\.

### Examples<a name="security_iam_service-with-iam-id-based-policies-examples"></a>



To view examples of Alexa for Business identity\-based policies, see [Alexa for Business identity\-based policy examples](security_iam_id-based-policy-examples.md)\.

## Alexa for Business resource\-based policies<a name="security_iam_service-with-iam-resource-based-policies"></a>

Alexa for Business does not support resource\-based policies\.

### <a name="security_iam_service-with-iam-resource-based-policies-examples"></a>

## Access control lists \(ACLs\)<a name="security_iam_service-with-iam-acls"></a>

Alexa for Business does not support Access Control Lists \(ACLs\)\.

## Authorization based on Alexa for Business tags<a name="security_iam_service-with-iam-tags"></a>

Alexa for Business does not support tagging resources or controlling access based on tags\.

## Alexa for Business IAM roles<a name="security_iam_service-with-iam-roles"></a>

An [IAM role](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html) is an entity within your AWS account that has specific permissions\.

### Using temporary credentials with Alexa for Business<a name="security_iam_service-with-iam-roles-tempcreds"></a>

You can use temporary credentials to sign in with federation, assume an IAM role, or to assume a cross\-account role\. You obtain temporary security credentials by calling AWS STS API operations such as [AssumeRole](https://docs.aws.amazon.com/STS/latest/APIReference/API_AssumeRole.html) or [GetFederationToken](https://docs.aws.amazon.com/STS/latest/APIReference/API_GetFederationToken.html)\. 

Alexa for Business supports using temporary credentials\. 

### Service\-linked roles<a name="security_iam_service-with-iam-roles-service-linked"></a>

Alexa for Business does not support service\-linked roles\.

### Service roles<a name="security_iam_service-with-iam-roles-service"></a>

This feature allows a service to assume a [service role](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html#iam-term-service-role) on your behalf\. This role allows the service to access resources in other services to complete an action on your behalf\. Service roles appear in your IAM account and are owned by the account\. This means that an IAM administrator can change the permissions for this role\. However, doing so might break the functionality of the service\.

Alexa for Business supports service roles\. 