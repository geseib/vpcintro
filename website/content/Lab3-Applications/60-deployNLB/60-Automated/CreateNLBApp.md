+++
title = "Launch Template"
chapter = false
weight = 50
+++

## Launch Template for NLB Application

We will use a cloudfromation template that builds out all of the components we could build manually above, creating a new NLB, Launch Temlates, Target Groups, Security groups, and Auto Scaling groups.. This type of Infrastrucutre as code can create consistent repeatable configurations, as well as provide a faster path to production.

1. Click on the CloudFormation Launch link below that corresponds to the AWS Region in which you want to deploy the workshop.

   [![US East (N. Virginia)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/us-east-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/review?stackName=VPC65-NLB&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/lab3nlb.yaml&param_AvailabilityZoneA=us-east-1a&param_AvailabilityZoneB=us-east-1b&param_ParentStack=VPC65&param_WhichVPC=VPC)
   

   ![Accept defaults](/images/2ndvpc-ack.png)
1. Leave the parameters at their defaults. Scroll down to the bottom of the **Quick create stack** screen and check the **I acknowledge that AWS CloudFormation might create IAM resources with custom names.** Click the **Create** button in the lower right.


1. After about 3-5 minutes, your VPC will be deployed with a new Application Environment. 
### You have completed the Launch NLB Application. ###

