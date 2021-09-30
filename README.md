# [olde800.com](https://olde800.com)

### hobby project website hosted on AWS using the following services:
- Route53
- S3
- CloudFront
- Certificate Manager
- CodePipeline (us-west-1)

*****

### Deployment Steps:
#### 1. S3
- create buckets, upload files, and enable static website hosting

#### 2. Cert Manager
- request a public cert

#### 3. CloudFront
- create a distribution

#### 4. Route 53
- create a hosted zone and records

#### 5. CodePipeline
- sync this repo and the **`www.olde800.com`** S3 bucket
- in the `us-west-1` region
