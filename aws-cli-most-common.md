# AWS CLI Most Common Commands Cheat Sheet

A quick reference for the most frequently used AWS CLI commands, organized by service. Each command is presented in a table with a code block for easy copy-paste.

---

## Account & Identity

| Description                   | Command                                                                                    |
| ----------------------------- | ------------------------------------------------------------------------------------------ |
| Get current AWS account ID    | `aws sts get-caller-identity --query Account --output text`                                |
| Get current user/role info    | `aws sts get-caller-identity`                                                              |
| Get current configured region | `aws configure get region`                                                                 |
| List all regions              | `aws ec2 describe-regions --query 'Regions[].RegionName' --output text`                    |
| List all availability zones   | `aws ec2 describe-availability-zones --query 'AvailabilityZones[].ZoneName' --output text` |

## STS (Security Token Service)

| Description                              | Command                                                                                                        |
| ---------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Get caller identity (account, user, ARN) | `aws sts get-caller-identity`                                                                                  |
| Assume a role                            | `aws sts assume-role --role-arn arn:aws:iam::ACCOUNT_ID:role/ROLE_NAME --role-session-name SESSION_NAME`       |
| Get session token (MFA)                  | `aws sts get-session-token --serial-number arn:aws:iam::ACCOUNT_ID:mfa/DEVICE_NAME --token-code CODE_FROM_MFA` |
| Decode authorization message             | `aws sts decode-authorization-message --encoded-message ENCODED_MESSAGE`                                       |

## S3 (Simple Storage Service)

| Description                    | Command                                               |
| ------------------------------ | ----------------------------------------------------- |
| List all buckets               | `aws s3 ls`                                           |
| List bucket contents           | `aws s3 ls s3://bucket-name/`                         |
| Upload file to S3              | `aws s3 cp file.txt s3://bucket-name/`                |
| Download file from S3          | `aws s3 cp s3://bucket-name/file.txt ./`              |
| Sync local dir to S3           | `aws s3 sync ./local-dir s3://bucket-name/remote-dir` |
| Create bucket                  | `aws s3 mb s3://bucket-name`                          |
| Remove bucket                  | `aws s3 rb s3://bucket-name`                          |
| Remove bucket and all contents | `aws s3 rb s3://bucket-name --force`                  |
| Get bucket region              | `aws s3api get-bucket-location --bucket bucket-name`  |

---

## EC2 (Elastic Compute Cloud)

| Description          | Command                                                          |
| -------------------- | ---------------------------------------------------------------- |
| List all instances   | `aws ec2 describe-instances --output table`                      |
| Start instance       | `aws ec2 start-instances --instance-ids i-1234567890abcdef0`     |
| Stop instance        | `aws ec2 stop-instances --instance-ids i-1234567890abcdef0`      |
| Terminate instance   | `aws ec2 terminate-instances --instance-ids i-1234567890abcdef0` |
| List security groups | `aws ec2 describe-security-groups --output table`                |
| List key pairs       | `aws ec2 describe-key-pairs --output table`                      |

---

## IAM (Identity and Access Management)

| Description           | Command                                         |
| --------------------- | ----------------------------------------------- |
| List all users        | `aws iam list-users --output table`             |
| List all roles        | `aws iam list-roles --output table`             |
| Get user details      | `aws iam get-user --user-name username`         |
| List user access keys | `aws iam list-access-keys --user-name username` |

---

## Lambda

| Description          | Command                                                                      |
| -------------------- | ---------------------------------------------------------------------------- |
| List all functions   | `aws lambda list-functions --query 'Functions[].FunctionName' --output text` |
| Get function details | `aws lambda get-function --function-name function-name`                      |
| Invoke function      | `aws lambda invoke --function-name function-name response.json`              |

---

## CloudFormation

| Description       | Command                                                                                                              |
| ----------------- | -------------------------------------------------------------------------------------------------------------------- |
| List all stacks   | `aws cloudformation list-stacks --query 'StackSummaries[?StackStatus!=\`DELETE_COMPLETE\`].StackName' --output text` |
| Get stack details | `aws cloudformation describe-stacks --stack-name stack-name`                                                         |
| Create stack      | `aws cloudformation create-stack --stack-name my-stack --template-body file://template.json`                         |
| Delete stack      | `aws cloudformation delete-stack --stack-name stack-name`                                                            |

---

## Resource Discovery

| Description | Command |
|-------------|---------|
| List all tagged resources across services in your account/region | `aws resourcegroupstaggingapi get-resources` |

---

## General CLI Options

| Description                   | Command                                         |
| ----------------------------- | ----------------------------------------------- |
| Configure AWS CLI             | `aws configure`                                 |
| Set region for single command | `aws ec2 describe-instances --region us-east-1` |
| Use named profile             | `aws s3 ls --profile profile-name`              |
| Output as table               | `--output table`                                |
| Output as JSON                | `--output json`                                 |
| Output as text                | `--output text`                                 |

---

For more, see the [official AWS CLI documentation](https://docs.aws.amazon.com/cli/latest/reference/).
