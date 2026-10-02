# IAM - Governance (Identity and Access Management)

## What is IAM?
AWS Identity and Access Management (IAM) is a web service that helps you securely control access to AWS resources. It lets you manage who is authenticated (signed in) and authorized (has permissions) to use resources.

## Key Concepts

- **Users:** An entity that you create in AWS to represent the person or application that uses it to interact with AWS. A user consists of a name and credentials.
- **Groups:** A collection of IAM users. Groups let you specify permissions for multiple users, which can make it easier to manage the permissions for those users.
- **Roles:** An IAM identity that you can create in your account that has specific permissions. An IAM role is similar to an IAM user, but it is not uniquely associated with one person. Instead, it is assumable by anyone who needs it (like an EC2 instance or an AWS service).
- **Policies:** A document in AWS that, when attached to an identity or resource, defines their permissions. Policies are written in JSON.
- **Permissions:** Define what actions are allowed or denied on specific AWS resources.

## Core Principles

- **Least privilege:** The security principle of granting only the minimum permissions necessary for a user or role to perform their intended tasks. This minimizes the risk of unauthorized access or accidental damage.

## IAM Best Practices
- Lock away your AWS account root user access keys.
- Create individual IAM users instead of sharing credentials.
- Use IAM groups to assign permissions.
- Grant least privilege.
- Enable MFA (Multi-Factor Authentication) for privileged users.
- Use IAM roles for applications that run on AWS EC2 instances.
- Rotate credentials regularly.

## Common Use Cases
- Allowing developers to access specific AWS services (like S3 or EC2) without using the root account.
- Giving an EC2 instance the ability to read files from an S3 bucket securely using a Role.
- Providing cross-account access for third-party auditing tools.
