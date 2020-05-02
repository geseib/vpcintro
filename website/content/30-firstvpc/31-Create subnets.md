+++
title = "Create Subnets"
chapter = false
weight = 31
+++

## Create Subnets

### We will create four(4) subnets: ###
2 Public: **PublicA** and **Public B** | 
2 Private: **PrivateA** and **Private B**  

   Subnet Name | Availability Zone | CIDR block
   ------------| ------------------|----------
**PublicA**|us-east-1a|10.64.0.0/24
**PublicB**|us-east-1b|10.64.1.0/24
**PrivateA**|us-east-1a|10.64.2.0/24
**PrivateB**|us-east-1b|10.64.3.0/24



1. From the **Amazon VPC** console and from the left menu select **Subnets**.
_You will see the subnets for the default VPC (1 for each Availability Zone in the region)_
![Default subnets](/images/createsubnets-defaultsubnets.png)

1. Click the **Create subnet** button.

1. Create **Public A** subnet in **Availability Zone A** with the following settings:
    - **Name tag**: **PublicA.
    - **VPC**: select **_your vpc_** name from the VPC dropdown list.
    - **Availability Zone**: **us-east-1a**
    - **IPv4 CIDR block**: **10.64.0.0/24** 
![Public A subnet](/images/createsubnets-publica.png)
1. Click the ***create** button.
![Public Subnet complete](/images/createsubnets-publicacreated.png)

1. After the subnet is created click the **close** button.

1. Repeat the process for the remaining 3 subnets. Make sure to set the Availability Zone and the CIDR block correctly.

    Subnet Name | Availability Zone | CIDR block
     ------------| ------------------|----------
    PublicB|us-east-1b|10.64.1.0/24
    PrivateA|us-east-1a|10.64.2.0/24
    PrivateB|us-east-1b|10.64.3.0/24

1. When you are done, the VPC subnets console should list all four subnets for your VPC. ![ALl Subnets Complete](/images/createsubnets-complete.png)

### You have completed the Subnet creation. ###
