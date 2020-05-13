+++
title = "Lab 3: App Sharing"
chapter = true
weight = 30
+++

## Lab 3 Application Availability and Scalability


Lets build a network load balanced, auto scaling group of EC2 instance built using a Launch Template. Using **Network Load Balancer** not only provides availablity and scalability to our application, but we can use it to share our application to other VPCs via **AWS Privatelink**.

#### What you will build:
1. **Network Load Balancer** with an Auto Scaling group of EC2 Instance built from a template
2. **VPC Endpoint Service**: making the application available for other VPCs to consume
3. **VPC Endpoint**: Consume the application from another VPC, without going over the TGW