# [olde800.com](https://olde800.com)

### Hobby project website hosted on AWS using the following services:

- S3
- Certificate Manager
- CloudFront
- Route53
- CodePipeline

*****

### Deployment Steps:
#### 1. S3
- create `olde800.com` and `www.olde800.com` buckets
- enable static website hosting on the `www.olde800.com` bucket

#### 2. Cert Manager
- request a public cert for `www.olde800.com` and `olde800.com` domains
- must be in the `us-east-1` region

#### 3. CloudFront
- create a distribution with `www.olde800.com.s3.amazonaws.com` as the origin
- associate the cert created above
- configure OAI (Origin Access Identity) to restrict S3 access to only CloudFront

#### 4. Route 53
- create a hosted zone and records
- `www.olde800.com` > `cloudfront distro`
- `olde800.com` > `www.olde800.com`

#### 5. CodePipeline
- sync this repo and the `www.olde800.com` S3 bucket
- currently in the `us-west-1` region
