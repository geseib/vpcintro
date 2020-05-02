+++
title = "Launch Template"
chapter = false
weight = 50
+++

## Launch Template

IAM Roles can be used as Instance Profiles, giving the EC2 instance permissions. This could be to access Amazon S3 for object storage or DynamoDB for NoSql quries. In this case we are using it for remote bash access using AWS Systems Manager.

1. Click on the CloudFormation Launch link below that corresponds to the AWS Region in which you want to deploy the workshop. _note: if you are sharing an account with someone else be sure to pick differnt regions._

   [![US East (N. Virginia)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/us-east-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/review?stackName=myvpc2&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/networkingdemos-vpcintro.yml&param_AvailabilityZoneA=us-east-1a&param_AvailabilityZoneB=us-east-1b&VPCCIDR=10.65.0.0\/16)

1. Scroll down to the bottom of the **Review name_of_your_stack** and check the **I acknowledge that AWS CloudFormation might create IAM resources with custom names.** Click the **Create** button in the lower right.

1. After about 3-5 minutes, your VPC will be deployed.
### You have completed the Launch VPC. ###

