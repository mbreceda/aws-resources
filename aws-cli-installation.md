# AWS CLI Installation & Account Setup Guide

This guide will help you install the AWS Command Line Interface (CLI) and set up your AWS account securely for Free Tier and AWS SDK learning.

---

## 1. Prerequisites

- Supported OS: Windows, macOS, or Linux
- Python 3.6+ (for AWS CLI v2, Python is bundled)
- Administrator or sudo privileges

---

## 2. Best Practices: Choosing an Email for AWS Free Tier

When creating an AWS account for Free Tier and AWS SDK learning, follow these tips for your email address:

- Use a unique email dedicated to this purpose (not your main/personal email)
- Ensure the email is private and only accessible by you
- Monitor the email regularly for AWS notifications
- Secure the email with a strong password and enable multi-factor authentication (MFA)

**Recommended email formats:**

- aws.sdk.lab+freetier@gmail.com
- aws.sdk.demo+cloud@gmail.com

If using Gmail, the `+tag` lets you create unique addresses that still deliver to your main inbox (e.g., youraddress+awsfreetier@gmail.com).

**Do not use:**

- Public, shared, or fake emails
- Emails you cannot recover or access

Always ensure you can recover the account if needed.

---

## 3. AWS CLI Installation Steps

### Windows

1. Download the AWS CLI MSI installer:
   - [AWS CLI v2 MSI Installer for Windows (64-bit)](https://awscli.amazonaws.com/AWSCLIV2.msi)
2. Double-click the downloaded `.msi` file and follow the installation prompts.
3. After installation, open a new terminal (Command Prompt, PowerShell, or Git Bash) and run:

   ```bash
   aws --version
   ```

   You should see output similar to:

   ```
   aws-cli/2.x.x Python/3.x.x ...
   ```

**Note:** Do not use the Linux installer (`awscliv2.zip`) on Windows. If you see errors like `cannot execute binary file: Exec format error`, you are using the wrong installer.

### macOS/Linux

1. Download the installer:
   ```bash
   curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
   ```
2. Unzip the installer:
   ```bash
   unzip awscliv2.zip
   ```
3. Run the installer:
   ```bash
   sudo ./aws/install
   ```
4. Verify the installation:
   ```bash
   aws --version
   ```
   You should see output similar to:
   ```
   aws-cli/2.x.x Python/3.x.x ...
   ```

---

## 4. Next Steps

- [Configure the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html) with your credentials:

  ```bash
  aws configure
  ```

---

## 5. Optional: Install AWS CDK Extension

To enhance your development experience, you can install the AWS Cloud Development Kit (CDK) extension for your code editor:

### For Visual Studio Code

- Open the Extensions view (`Ctrl+Shift+X`).
- Search for `AWS Toolkit` and install it. This extension provides AWS CDK support and other AWS features.
- [AWS Toolkit for VS Code - Marketplace](https://marketplace.visualstudio.com/items?itemName=AmazonWebServices.aws-toolkit-vscode)

---

For more details, visit the [official AWS CLI documentation](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html).
