# Serverless AWS Region Mappings
Ready-to-use AWS CloudFormation Mappings for use in [serverless](https://github.com/serverless/serverless) projects. Makes using `Fn::FindInMap` with AWS region-specific resources a cinch.

## Getting started
These mappings are meant to be referenced in a [serverless.yml](https://serverless.com/framework/docs/providers/aws/guide/serverless.yml/) file.

In your serverless.yml file

```yaml
service: serverless-service

# Additional configuration ...

resources:
  # Make sure not to nest a Mapping in a Resources object
  # API Gateway Mappings
  - ${file(./mappings/api-gateway-region-hosted-zone-map.yml)}
  # CloudFront Mappings
  - ${file(./mappings/cloudfront-region-hosted-zone-map.yml)}
  # ELB Mappings
  - ${file(./mappings/elb-region-hosted-zone-map.yml)}
  # S3 Static Website Mappings
  - ${file(./mappings/s3-static-website-region-hosted-zone-map.yml)}
  - Resources:
  # Additional resources ...
```

You can use as many Mappings as needed in resources section.

### Available mappings
There are currently region mappings for AWS API Gateway, AWS CloudFront, AWS Elastic Load Balancer, and AWS S3 Static Website.

Note that some regions may be missing either due to AWS not supporting all features in all regions, or simple error.

> Note: Each map uses the AWS Region (i.e. us-east-1, ap-northeast-3, etc.) as a Top Level Key

| Map Name | Second Level Keys | Regions |
| -------- | ---- | ------- |
| APIGatewayRegionHostedZoneMap | `Endpoint`, `HostedZoneID` | `us-east-2`, `us-east-1`, `us-west-1`, `us-west-2`, `ap-south-1`, `ap-northeast-3`,`ap-northeast-2`, `ap-southeast-1`, `ap-southeast-2`, `ap-northeast-1`, `ca-central-1`,`eu-central-1`, `eu-west-1`, `eu-west-2`, `eu-west-3`, `eu-north-1`, `sa-east-1` |
| CloudFrontRegionHostedZoneMap | `Endpoint`, `HostedZoneID` | `us-east-1` |
| ELBRegionHostedZoneMap | `ALBHostedZoneID`, `NLBHostedZoneID`, `Endpoint` | `us-east-2`, `us-east-1`, `us-west-1`, `us-west-2`, `ap-south-1`,`ap-northeast-3`, `ap-northeast-2`, `ap-southeast-1`, `ap-southeast-2`, `ap-northeast-1`,`ca-central-1`, `cn-north-1`, `cn-northwest-1`, `eu-central-1`, `eu-west-1`, `eu-west-2`,`eu-west-3`, `eu-north-1`, `sa-east-1` |
| S3StaticWebsiteRegionHostedZoneMap | `Endpoint`, `HostedZoneID` | `us-east-2`, `us-east-1`, `us-west-1`, `us-west-2`, `ap-south-1`,`ap-northeast-3`, `ap-northeast-2`, `ap-southeast-1`, `ap-southeast-2`, `ap-northeast-1`,`ca-central-1`, `eu-central-1`, `eu-west-1`, `eu-west-2`, `eu-west-3` |

## Contributing
Pull requests are welcome; there are many more AWS Region Mappings that could be added. Fork the repository, make your changes, then submit a pull request.

## Authors
* Alex Kube 