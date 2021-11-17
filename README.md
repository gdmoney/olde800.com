# [olde800.com](https://olde800.com)

### Hobby project website hosted on AWS using the following services:
- Route53
- S3
- CloudFront
- Certificate Manager
- CodePipeline

*****

### Deployment Steps:
#### 1. S3
- create `olde800.com` and `www.olde800.com` buckets
- enable static website hosting on the `www.olde800.com` bucket

#### 2. Cert Manager
- request a public cert
- in the `us-east-1` region

#### 3. CloudFront
- create a distribution
- associate a cert
- configure OAI (Origin Access Identity) to restrict S3 access

#### 4. Route 53
- create a hosted zone and records
- `www.olde800.com` > `cloudfront distro`
- `olde800.com` > `www.olde800.com`

#### 5. CodePipeline
- sync this repo and the `www.olde800.com` S3 bucket
- in the `us-west-1` region
