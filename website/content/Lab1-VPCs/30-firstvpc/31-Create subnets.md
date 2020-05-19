+++
title = "Create Subnets"
chapter = false
weight = 31
+++

## Create Subnets

### We will create four(4) subnets: ###
Two Public: **VPC64-PublicA** and **VPC64-PublicB** | 
Two Private: **VPC64-PrivateA** and **VPC64-PrivateB**  

   Subnet Name | Availability Zone | CIDR block
   ------------| ------------------|----------
**VPC64-PublicA**|us-east-1a|`10.64.0.0/24`
**VPC64-PublicB**|us-east-1b|`10.64.1.0/24`
**VPC64-PrivateA**|us-east-1a|`10.64.2.0/24`
**VPC64-PrivateB**|us-east-1b|`10.64.3.0/24`



1. From the **Amazon VPC** console and from the left menu select **Subnets**.
_You will see the subnets for the default VPC (1 for each Availability Zone in the region)_
    ![Default subnets](/images/createsubnets-defaultsubnets.png)

1. Click the **Create subnet** button.

    ![Public A subnet](/images/createsubnets-publica.png)
1. Create **VPC64-Public A** subnet in **Availability Zone A** with the following settings:
    - **Name tag**: **VPC64-PublicA**.
    - **VPC**: select **_your vpc_** name from the dropdown list.
    - **Availability Zone**: **us-east-1a**
    - **IPv4 CIDR block**: **10.64.0.0/24** 

1. Click the ***create** button.
    ![Public Subnet complete](/images/createsubnets-publicacreated.png)

1. After the subnet is created click the **Close** button.

1. Repeat the process for the remaining 3 subnets. Make sure to set the Availability Zone and the CIDR block correctly.

    Subnet Name | Availability Zone | CIDR block
     ------------| ------------------|----------
    **VPC64-PublicB**|us-east-1b|`10.64.1.0/24`
    **VPC64-PrivateA**|us-east-1a|`10.64.2.0/24`
    **VPC64-PrivateB**|us-east-1b|`10.64.3.0/24`

1. When you are done, the VPC subnets console should list all four subnets for your VPC. 
    ![ALl Subnets Complete](/images/createsubnets-complete.png)

### You have completed the Subnet creation. ###
