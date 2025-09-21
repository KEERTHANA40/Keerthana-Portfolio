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
