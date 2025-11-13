# Using LocalStack for AWS Development

LocalStack is a tool that allows you to run a local AWS cloud stack on your machine. It emulates many AWS services, so you can develop and test your AWS applications without needing a real AWS account or incurring any costs.

---

## Why Use LocalStack?

- No need for a real AWS account or credentials
- No risk of unexpected charges
- Fast local development and testing
- Supports many core AWS services (S3, Lambda, DynamoDB, SQS, SNS, etc.)

---

## How to Set Up LocalStack

### 1. Install LocalStack (using pip)

```bash
pip install localstack
```

Or use Docker (recommended):

```bash
docker run -d -p 4566:4566 -p 4571:4571 localstack/localstack
```

### 2. Configure AWS CLI/SDK for LocalStack

- Use dummy credentials (LocalStack does not validate them):
  - AWS Access Key ID: test
  - AWS Secret Access Key: test
- Set the endpoint URL to point to LocalStack, e.g.:
  ```bash
  aws --endpoint-url=http://localhost:4566 s3 ls
  ```

### 3. Example: Using AWS CLI with LocalStack

```bash
aws --endpoint-url=http://localhost:4566 s3 mb s3://my-bucket
aws --endpoint-url=http://localhost:4566 s3 ls
```

---

## Limitations

- Not all AWS services are fully supported (see LocalStack docs for details)
- For production, always use real AWS

---

For more info, see the [LocalStack documentation](https://docs.localstack.cloud/).
