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












