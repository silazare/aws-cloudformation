## CloudFormation template for example ECS cluster infrastructure with microservices

Based on https://github.com/aws-samples/ecs-refarch-cloudformation repository

## NOT WORKING now - MongoDB connection issue, Microservices cross-connection issues

VPC deployment:
  - 2 public and private subnets across two Availabilty Zones.
  - Internet Gateway, with a default route on the public subnets.
  - 2 NAT Gateways (one in each AZ), and default routes for them in the private subnets.

ECS cluster deployment:
  - ECS cluster using an AutoScaling Group, with ECS hosts distributed
  across multiple Availability Zones.

ECS services deployment:
  - ECS Reddit services from Docker Hub images, source - https://github.com/silazare/reddit

How to use:
  - Update S3 URLs inside master.yaml, as now its hardcoded to my own S3
  - Upload all structure to AWS S3 bucket and point CloudFormation to master.yaml URL.
Or may use my S3 URL - https://s3.amazonaws.com/cf-template-structured/master.yaml and upload it to CloudFormation.
