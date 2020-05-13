+++
title = "Default VPC"
chapter = false
weight = 21
+++

## Default VPC

In every region there is a default VPC. In the us-east-1 region it will have 6 subnets across 6 Availability Zones.

![Default VPC](/images/defaultvpc_diagram.png)

1. Open the **Amazon VPC** console and from the left menu select **Your VPCs**.
   .
   ![Your VPCs](/images/defaultvpc_yourvpcs.png)

1. Take a look at the **default VPC**. It is using CIDR **172.31.0.0/16**.

   ![Your VPCs](/images/vpc-default-subnets.png)

1. From the menu on the left select **Subnets**. Take a look at the **default VPC**'s subnets.

   ![Your VPCs](/images/vpc-default-routes.png)

1. From the menu on the left select **Route Tables**. Below the list, click on the **Routes** tab. Take a look at the **default VPC**'s route table. There is the local VPC route for 172.31.0.0/16 and a default route 0.0.0.0/0 targeting the Internet Gateway. _All of the subnets in the default VPC are public subnets!_

   ![Your VPCs](/images/vpc-default-igw.png)

1. From the menu on the left select **Internet Gateways**.  See that it is in a State **attached**. _When we create an Internet Gateway, we want to make sure to attach it to our VPC_.


## You have completed the Default VPC tour
Now that you have looked around a bit, it's time to build a VPC. 




