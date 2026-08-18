# Data Encryption in Backblaze B2

The notebook in this repository guides you through the different options for encrypting data in Backblaze B2, with Python examples that use the AWS SDK for Python (boto3).

[b2_encryption_demo.ipynb](b2_encryption_demo.ipynb)

## Configuration

The notebook uses the Backblaze B2 S3-compatible API by default. Copy `.env.example` to `.env` and fill in the standard B2 environment variables. `.env.example` is the authoritative list; the notebook validates the required subset before creating the S3 client.

Use a disposable demo bucket or prefix, not a production bucket root. The notebook writes every object under a fresh `b2-data-encryption-demo/<run-id>/` prefix, and the default-encryption demo restores the bucket's original encryption configuration in a `finally` block.

Install dependencies from the pinned `requirements.txt` file:

```bash
pip install -r requirements.txt
```

`B2_PUBLIC_URL_BASE` is optional and included only for consistency with other Backblaze B2 samples; this notebook does not read it because all operations use the S3-compatible API.

Every boto3 S3 client in the sample sets a Backblaze sample user agent with `(backblaze-b2-samples)` for auditability.
