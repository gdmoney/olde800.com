# [olde800.com](https://olde800.com)

## website hosted on AWS using the following services:
- Route53
- S3
- CloudFront
- Certificate Manager
- CodePipeline - automatically syncs this repository to the **`www.olde800.com`** S3 bucket

*****

## Deployment Steps:
### 1. S3
   - create buckets and enable static website hosting

### 2. Cert Manager
   - create a wildcard cert

### 3. CloudFront
   - create a distribution

### 4. Route 53
   - create A records

### 5. CodePipeline
   - link the GitHub repo and the S3 bucket
