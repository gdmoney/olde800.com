# [olde800.com](https://olde800.com)

### Hobby project website hosted on AWS using the following services:

- S3
- Certificate Manager
- CloudFront
- Route 53
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
- add `www.olde800.com` and `olde800.com` as alternate domain names
- associate the cert created above
- configure OAI (Origin Access Identity) to restrict S3 access to only CloudFront
- add `/error.html` as the response page path to the HTTP 403 error code
- *CloudFront caches S3 content for 24 hrs; use Invalidations to force update`index.html`*

#### 4. Route 53
- create a hosted zone and records
- A: `www.olde800.com` > Alias: `cloudfront distro`
- A: `olde800.com` > Alias: `www.olde800.com`

#### 5. CodePipeline
- create a new pipeline to sync this repo to the S3 bucket
- Source: `GitHub/gdmoney/olde800.com/master` > Deploy: `S3/www.olde800.com`
- currently in the `us-west-1` region
