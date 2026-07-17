# Data Encryption in Backblaze B2

The notebook in this repository guides you through the different options for encrypting data in Backblaze B2, with Python examples that use the AWS SDK for Python (boto3).

[b2_encryption_demo.ipynb](b2_encryption_demo.ipynb)

## Configuration

The notebook uses the Backblaze B2 S3-compatible API by default. Copy `.env.example` to `.env` and fill in the standard B2 environment variables:

- `B2_APPLICATION_KEY_ID`
- `B2_APPLICATION_KEY`
- `B2_BUCKET_NAME`
- `B2_REGION`
- `B2_PUBLIC_URL_BASE`

Every boto3 S3 client in the sample sets a Backblaze sample user agent with `(backblaze-b2-samples)` for auditability.
