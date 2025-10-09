buckets/objects, CLI examples.

# AWS S3 basics — Sept 19

## What is S3
- Amazon S3 is an object storage service. Files (objects) are stored inside buckets.

## Key concepts
- Bucket = top-level container (unique name).  
- Object = file + metadata (key identifies object).  
- Regions: bucket region matters for latency/cost.  
- Permissions: controlled via IAM roles/policies or bucket policy.

## Why S3 for DE pipelines
- Durable, cost-effective storage for raw & processed data.
- Supports parquet/delta + partitioning (speed & cost benefits).
- Integrates with Databricks, Glue, Athena, EMR.

## Example CLI (do not run unless AWS CLI configured)
# Upload a local file to S3
aws s3 cp my_data.csv s3://your-bucket/raw/my_data.csv

# List objects in a prefix
aws s3 ls s3://your-bucket/raw/
# AWS S3 — Basics (Sept 22)

- **What is a bucket?**
  A bucket is a top-level container in S3 used to store objects (files). Buckets are globally named per account and exist in a specific region.

- **What is an object?**
  An object is a file stored in a bucket; it has a key (path/name), metadata, and content.

- **IAM / Access basics**
  Access to buckets/objects is controlled via IAM users/roles and bucket policies. Use least-privilege: grant only the actions needed (e.g., s3:GetObject for reads).

- **Example CLI command**
  List buckets:

# AWS S3 — Practical Notes (Oct 7)

- Upload example:
  aws s3 cp localfile.csv s3://your-bucket-name/data/localfile.csv

- IAM principle: use roles for compute, not static user keys.

- Minimal workflow:
  1. Raw → s3://company-raw/<dataset>/date=YYYY-MM-DD/
  2. ETL → s3://company-processed/<dataset>/
  3. Catalog → Glue or Unity Catalog points to processed data.
