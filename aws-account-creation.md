## 10. Creating a New AWS CDK Project (Python or TypeScript)

To start a new AWS Cloud Development Kit (CDK) project, you can use either Python or TypeScript as your language. Use the following commands:

1. Install the AWS CDK CLI if you haven't already:

   ```bash
   npm install -g aws-cdk
   ```

2. Create a new directory for your project and navigate into it:

   ```bash
   mkdir my-cdk-project
   cd my-cdk-project
   ```

3. Initialize a new CDK project:
   - For Python:
     ```bash
     cdk init app --language python
     ```
   - For TypeScript:
     ```bash
     cdk init app --language typescript
     ```

This will set up a new CDK project structure in your chosen language. Follow the prompts to complete the setup, then install the required dependencies as instructed in the generated README file.

---

## 9. Removing CloudFormation Template Files from S3 Buckets

When you deploy resources using CloudFormation, the template file (such as `2025-11-13T002258.728Zty4-s3template.json`) may also be uploaded to your S3 bucket. These files are not deleted automatically and should be removed to keep your bucket clean and avoid unnecessary storage costs.

+To delete a specific template file from your S3 bucket, use the following AWS CLI command (with your actual bucket and file name):

- +`bash
+aws s3 rm s3://cf-templates-jj9t1tsbr0rr-us-east-2/2025-11-13T002258.728Zty4-s3template.json
+`
- +This command will delete only the specified file from the bucket. Remember to remove any other template files you no longer need.

  ***

# AWS Account Creation & S3 Management Guide

This guide walks you through creating a new AWS account, securing it, preparing it for AWS CLI/SDK use with Free Tier, and managing S3 buckets safely and efficiently.

---

## 1. Prepare Your Information

- Valid, private email address (see best practices in the installation guide)
- Strong password
- Phone number for verification
- Credit/debit card (required for identity verification, even for Free Tier)

---

## 2. Create Your AWS Account

1. Go to the [AWS Signup Page](https://portal.aws.amazon.com/billing/signup)
2. Click **Create a new AWS account**
3. Enter your email address, password, and choose an account name (e.g., aws-sdk-freetier)
4. Click **Continue**
5. Choose **Personal** or **Business** account type
6. Fill in your full name, phone number, and address
7. Agree to the terms and conditions
8. Enter your credit/debit card details (AWS will make a small, temporary charge for verification)
9. Choose your preferred identity verification method (SMS or voice call) and enter the code sent to your phone
10. Select the **Basic Support** (free) plan unless you need premium support

---

## 3. Secure Your Root Account

- Sign in to the AWS Management Console with your root account
- Set up Multi-Factor Authentication (MFA) for added security
- Review your account settings

---

## 4. Create an IAM User for Administration

To avoid using your root account for daily tasks, create an IAM user with administrative privileges:

1. In the AWS Console, go to **IAM** (Identity and Access Management)
2. Click **Users** > **Add users**
3. Enter a username (e.g., `admin-user` or `cli-access`)
4. Select **Provide user access to the AWS Management Console** and set a password if you want console access
5. On the **Set permissions** step:
   - Choose **Attach policies directly**
   - In the list, search for and check **AdministratorAccess**
   - (See screenshot above for reference)
6. Complete the steps and save the user credentials
7. Sign in as this IAM user for all regular AWS work

---

## 5. Add Security Credentials to Your IAM User

After creating your IAM user, set up security credentials for secure access:

1. Go to the **Security credentials** tab for your IAM user
2. (Optional but recommended) Click **Assign MFA device** to enable Multi-Factor Authentication (MFA) for extra security. Follow the prompts to register your authenticator app or hardware device
3. To use the AWS CLI or SDKs, create an access key:

   - Click **Create access key** under the Access keys section
   - On the **Retrieve access keys** screen, copy or download your Access Key ID and Secret Access Key. This is the only time you will see the secret key. (See screenshot above for reference)
   - You can also download a `.csv` file with your credentials for safekeeping

4. Use these credentials to configure the AWS CLI:
   - Open your terminal and run:
     ```bash
     aws configure
     ```
   - When prompted, enter your **AWS Access Key ID** and **AWS Secret Access Key** (from the previous step)
   - You will also be asked for your default region and output format. Example values:
     - Default region name: `eu-west-1`
     - Default output format: `json`
   - (See screenshot above for reference)

### Access Key Best Practices

- Never store your access key in plain text, in a code repository, or in code
- Disable or delete access keys when no longer needed
- Enable least-privilege permissions
- Rotate access keys regularly

For more details, see the [best practices for managing AWS access keys](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html#Using_CreateAccessKey)

---

## 6. Start Using AWS Free Tier

- Explore AWS services from the console
- Monitor your Free Tier usage to avoid unexpected charges

---

## 7. Automatically Clean Up S3 Buckets with Lifecycle Rules

To avoid unnecessary storage costs or to keep test environments tidy, you can configure your S3 bucket to automatically delete its contents after a set period using a lifecycle rule in your CloudFormation template.

**Example CloudFormation snippet to expire all objects in a bucket after 1 day:**

```json
{
  "Resources": {
    "MyS3Bucket": {
      "Type": "AWS::S3::Bucket",
      "Properties": {
        "LifecycleConfiguration": {
          "Rules": [
            {
              "Status": "Enabled",
              "ExpirationInDays": 1
            }
          ]
        }
      }
    }
  }
}
```

This ensures all objects in the bucket are automatically deleted 1 day after creation. Adjust `ExpirationInDays` as needed for your use case.

---

## 8. Deleting an S3 Bucket Using the AWS CLI

If you need to completely remove an S3 bucket and all its contents, use the AWS CLI:

```bash
aws s3 rb s3://your-bucket-name --force
```

- Replace `your-bucket-name` with the actual name of your bucket.
- The `--force` flag deletes all objects in the bucket before removing the bucket itself.

**Warning:** This action is irreversible. All data in the bucket will be permanently deleted.

---

For more details, see the [AWS Free Tier FAQ](https://aws.amazon.com/free/free-tier-faqs/) and [AWS Account Creation Docs](https://docs.aws.amazon.com/accounts/latest/reference/manage-acct-creating.html)
