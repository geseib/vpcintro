+++
menutitle = "AWS PrivateLink"
chapter = false
weight = 70
+++

## Create an AWS PrivateLink

PrivateLink is made of two parts: the Producer components and the Consumer components. The Producer will have a Network Load Balanced application that can be shared using a VPC Endpoint service. The Consumer will have a VPC Endpoint that connects to the Endpoint Service. THe VPC endpoint creates Elastic Network Interfaces in the Consumers VPC.


![PrivateLink Diagram](/images/pl-diagram.png)

#### We will complete the following steps:
1. Create a **VPC Endpoint Service** in the 10.65.0.0/16 VPC

1. Create a **VPC Endpoint** in the 10.64.0.0/16 VPC

1. Test connectivity between VPCs

