# AWS CDK Most Common Commands Cheat Sheet

A quick reference for the most frequently used AWS Cloud Development Kit (CDK) commands, organized in a table for easy copy-paste and learning.

---

| Description                                        | Command                                 |
| -------------------------------------------------- | --------------------------------------- |
| Initialize a new CDK project (TypeScript)          | `cdk init app --language typescript`    |
| Initialize a new CDK project (Python)              | `cdk init app --language python`        |
| Bootstrap your AWS environment for CDK deployments | `cdk bootstrap aws://ACCOUNT_ID/REGION` |
| Synthesize CloudFormation template from your app   | `cdk synth`                             |
| Deploy the CDK stack(s) to your AWS account        | `cdk deploy`                            |
| Deploy a specific stack                            | `cdk deploy stack-name`                 |
| List all stacks in the app                         | `cdk list`                              |
| Destroy the deployed stack(s)                      | `cdk destroy`                           |
| Destroy a specific stack                           | `cdk destroy stack-name`                |
| Diff: compare deployed stack with local changes    | `cdk diff`                              |
| Add a new library dependency (TypeScript)          | `npm install @aws-cdk/aws-s3`           |
| Add a new library dependency (Python)              | `pip install aws-cdk.aws-s3`            |
| View CDK version                                   | `cdk --version`                         |
| Get help for CDK commands                          | `cdk --help`                            |

---

**Notes:**

- Replace `ACCOUNT_ID` and `REGION` in the bootstrap command with your actual AWS account ID and region.
- Use the appropriate dependency install command for your language (npm for TypeScript, pip for Python).
- For more, see the [official AWS CDK documentation](https://docs.aws.amazon.com/cdk/latest/guide/cli.html).
