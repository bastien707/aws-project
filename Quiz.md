# Quiz

## IAM

***Which statement describes AWS Identity and Access Management (IAM)
users?***

Every IAM user for an account must have a unique name.

***How can you grant the same level of permissions to multiple users within an account?***

Apply an AWS Identity and Access Management (IAM) policy to an IAM group.

***Which statements describe AWS Identity and Access Management (IAM)
roles? (Select TWO)***

Options 3 and 4: They can be assumed by individuals, applications, and services and they provide temporary security credentials.

***Which statement describes a resource-based policy?***

Option 1: It can be applied to any AWS resource.

***How does AWS Identity and Access Management (IAM) evaluate a policy?***

Option 1: It checks for explicit allow statements before it checks for explicit deny statements.

***A team of developers needs access to several services and resources in a virtual private cloud (VPC) for 9 months. How can you use AWS Identity and Access Management (IAM) to enable access for them?***

Option 3: Create an IAM user for each developer, put them all in an IAM group, and attach the required IAM policies to the IAM group.

***How does identity federation increase security for an application that is built in Amazon Web Services (AWS)?***

Option 1: Users can use single sign-on (SSO) to access the application through an existing authenticated identity.

## Network

***Which definition describes a virtual private cloud (VPC)?***

Option 3: A logically isolated virtual network that you define in the AWS Cloud.

***A company's VPC has the CIDR block 172.16.0.0/21 (2048 addresses). It has two subnets (A and B). Each subnet must support 100 usable addresses now, but this number is expected to rise to at most 254 usable addresses soon. Which subnet addressing scheme meets the requirements and follows AWS best practices?***

Option C: Subnet A: 172.16.0.0/23 (512 addresses) Subnet B: 172.16.2.0/23 (512 addresses)

***Which combination of actions enables direct internet access for IPv4 hosts in a virtual private cloud (VPC)?***

Option 1: Creating a route for 0.0.0.0/0 that points to the internet gateway.

Option 3: Configuring hosts to have or obtain an internet-routable address.

Option 6: Configuring security groups and network access control lists (network ACLs) to permit internet traffic.

***Several EC2 instances launch in a virtual private cloud (VPC) that has internet access. These instances should not be accessible from the internet, but they must be able to download updates from the internet. How should the instances launch?***

Option 4: Without public IP addresses, in a subnet with a default route to a network address translation (NAT) gateway.

## Policies evaluation

**Question: What actions are allowed for EC2 instances and S3 objects based on this policy? What specific resources are included?**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowEC2AndS3",
      "Effect": "Allow",
      "Action": [
        "ec2:RunInstances",
        "ec2:TerminateInstances",
        "s3:GetObject",
        "s3:PutObject"
      ],
      "Resource": [
        "arn:aws:ec2:us-east-1:123456789012:instance/*",
        "arn:aws:s3:::example-bucket/*"
      ]
    }
  ]
}
```

This policy allows specific actions for both EC2 instances and S3 objects. The actions that are allowed include "ec2:RunInstances" and "ec2:TerminateInstances" for EC2 instances, and "s3:GetObject" and "s3:PutObject" for S3 objects. The policy grants permission to run and terminate instances within the `us-east-1` region under the AWS account `123456789012`, as specified by the resource ARN "arn:aws:ec2:us-east-1:123456789012:instance/*". Additionally, it allows getting and putting objects within the "example-bucket" in S3, as indicated by the resource ARN "arn:aws:s3:::example-bucket/*".

**Question: Under what condition does this policy allow access to VPC-related information? Which AWS region is specified?**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowVPCAccess",
      "Effect": "Allow",
      "Action": [
        "ec2:DescribeVpcs",
        "ec2:DescribeSubnets",
        "ec2:DescribeSecurityGroups"
      ],
      "Resource": "*",
      "Condition": {
        "StringEquals": {
          "aws:RequestedRegion": "us-west-2"
        }
      }
    }
  ]
}
```

This policy allows access to VPC-related information under the condition that the requested region is "us-west-2". The policy grants permission for the following actions: "ec2:DescribeVpcs", "ec2:DescribeSubnets", and "ec2:DescribeSecurityGroups". The specified resources for these actions are set to "*", meaning that the policy applies to all resources within the EC2 service. Notice that the access to VPC-related information is only allowed when the requested region matches "us-west-2".

**Question: What actions are allowed on the "example-bucket" and its objects based on this policy? What specific prefixes are specified in the condition?**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowS3ReadWrite",
      "Effect": "Allow",
      "Action": ["s3:GetObject", "s3:PutObject", "s3:ListBucket"],
      "Resource": [
        "arn:aws:s3:::example-bucket",
        "arn:aws:s3:::example-bucket/*"
      ],
      "Condition": {
        "StringLike": {
          "s3:prefix": ["documents/*", "images/*"]
        }
      }
    }
  ]
}
```

The actions allowed on the "example-bucket" and its objects are s3:GetObject (reading), s3:PutObject (writing), and s3:ListBucket (listing). The policy specifies two specific prefixes in the condition: "documents/*" and "images/*". These prefixes restrict the actions to objects within the "example-bucket" that have either "documents/" or "images/" as their prefix. Any other objects in the bucket would not be allowed for these actions.

**Question: What actions are allowed for IAM users based on this policy? How are the resource ARNs constructed?**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowIAMUserCreation",
      "Effect": "Allow",
      "Action": "iam:CreateUser",
      "Resource": "arn:aws:iam::123456789012:user/${aws:username}"
    },
    {
      "Sid": "AllowIAMUserDeletion",
      "Effect": "Allow",
      "Action": "iam:DeleteUser",
      "Resource": "arn:aws:iam::123456789012:user/${aws:username}"
    }
  ]
}
```

IAM users are allowed two actions: iam:CreateUser for creating IAM users and iam:DeleteUser for deleting IAM users. The resource ARNs in the policy are constructed using the format "arn:aws:iam::123456789012:user/${aws:username}". The ${aws:username} placeholder is dynamically replaced with the username of the IAM user making the request, ensuring that the actions are only allowed for the specific IAM user associated with the credentials used.

***Questions: Which AWS service does this policy grant you access to? Does it allow you to create an IAM user, group, policy, or role? Go to https://docs.aws.amazon.com/IAM/latest/UserGuide/ and in the left navigation expand Reference > Policy Reference > Actions, Resources, and Condition Keys. Choose Identity And Access Management. Scroll to the Actions Defined by Identity And Access Management list.��Name at least three specific actions that the iam:Get* action allows.***

```json
{
  "Version": "2012-10-17",
  "Statement": {
    "Effect": "Allow",
    "Action": ["iam:Get*", "iam:List*"],
    "Resource": "*"
  }
}
```

The provided policy grants access to the AWS Identity and Access Management (IAM) service, allowing the creation and management of IAM entities. Specifically, it allows the "iam:Get*" action, which includes permissions to retrieve information about IAM users, groups, policies, and roles. This implies the ability to create and manage these entities. Additionally, the "iam:List*" action is permitted, enabling the listing of IAM entities. These permissions provide comprehensive access to IAM resources, facilitating the administration of IAM users, groups, policies, and roles within the AWS environment.

**Questions: What actions does the policy allow? Say that the policy included an additional statement object, like this example:**

```
{
  "Effect": "Allow",
  "Action": "ec2:*"
}
```
**How would the policy restrict the access granted to you by this additional statement?
If the policy included both the statement on the left and the statement in question 2, could you terminate an m3.xlarge instance that existed in the account?***

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Condition": {
        "StringEquals": {
          "ec2:InstanceType": ["t2.micro", "t2.small"]
        }
      },
      "Resource": "arn:aws:ec2:*:*:instance/*",
      "Action": ["ec2:RunInstances", "ec2:StartInstances"],
      "Effect": "Deny"
    }
  ]
}
```

The provided policy allows the actions "ec2:RunInstances" and "ec2:StartInstances" on EC2 instances. However, if the policy included an additional statement object like the example you provided, which allows all "ec2:*" actions, the access granted by the original policy would be restricted. The new statement would override the "Deny" effect of the original statement, allowing all EC2 actions to be permitted.

In the case where the policy includes both the original statement and the additional statement allowing all EC2 actions, you would be able to terminate an m3.xlarge instance that existed in the account. This is because the "ec2:TerminateInstances" action is covered by the "ec2:*" wildcard action in the additional statement, which allows all EC2 actions to be performed.









