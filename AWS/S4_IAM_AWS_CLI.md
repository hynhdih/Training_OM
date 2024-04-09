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
