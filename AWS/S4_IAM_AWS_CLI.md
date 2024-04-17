# I. IAM - Identity and Access Management
  - Account Alias: Tạo bí danh cho user
  - IAM Policies Structure:
    - Consists of:
      - Version: policy language version, always include “2012-10-17”
      - Id: an identifier for the policy (optional)
      - Statement: one or more individual statements (required)
    -  Statements consists of:
      - Sid: an identifier for the statement (optional)
      - Effect: whether the statement allows or denies access (Allow, Deny)
      - Principal: account/user/role to which this policy applied to
      - Action: list of actions this policy allows or denies
      - Resource: list of resources to which the actions applied to
      - Condition: conditions for when this policy is in effect (optional)
        <img src="https://github.com/hynhdih/Training_OM/assets/82271913/59a799c1-779b-4206-bc60-161fc0328e59" width="500" height="500">

# II. Policies IAM
## 1. Administrator Access
  - Full access at All resource
  - Permissions defined in this policy (JSON):
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "*",
            "Resource": "*"
        }
    ]
}
```
  - *: any action on any resource
## 2. IAMReadOnlyAccess
  - Full: List Limited: Read at All resources
  - Permissions defined in this policy (JSON):
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "iam:GenerateCredentialReport",
                "iam:GenerateServiceLastAccessedDetails",
                "iam:Get*",
                "iam:List*",
                "iam:SimulateCustomPolicy",
                "iam:SimulatePrincipalPolicy"
            ],
            "Resource": "*"
        }
    ]
}
```
## 3. Multi Fact or Authentication - MFA
  - MFA = password you know + security device you own
  - MFA devices options in AWS
  - 3 options to access AWS:
    - AWS Management Console (protected by password +MFA)
    - AWS Command Line Interface (CLI): protected by access keys
    - AWS Software Developer Kit (SDK) - for code: protected by access keys
  - With: Access Key ID ~ username
          Secret Access Key ~ password
  - List user by CLI:
    ```
    aws iam list-users
    ```
## 4. AWS Cloudshell
- cloud shell is basically a terminal in the cloud of AWS
- This is going to return for you an API call as if the credentials being used, where the credentials of the accounts of you using the cloud right now
## 5. IAM Roles
- EC2
- Lambda, ...
- An IAM role is an IAM identity that you can create in your account that has specific permissions.
- An IAM role is similar to an IAM user, in that it is an AWS identity with permission policies that determine what the identity can and cannot do in AWS.
- However, instead of being uniquely associated with one person, a role is intended to be assumable by anyone who needs it.
- Also, a role does not have standard long-term credentials such as a password or access keys associated with it. Instead, when you assume a role, it provides you with temporary security credentials for your role session.
## 6. IAM Security Tools
• IAM Credentials Report (account-level)
  - a report that lists all your account's users and the status of their various credentials
• IAM Access Advisor (user-level)
  - Access advisor shows the ser vice permissions granted to a user and when those services were last accessed.
• You can use this information to revise your policies.
## 7. IAM Guidelines & Best Practices
- Don’t use the root account except for AWS account setup
- One physical user = One AWS use
**- Use the root account only to create your first IAM User and a few account/service management tasks. For everyday tasks, use an IAM User.**
