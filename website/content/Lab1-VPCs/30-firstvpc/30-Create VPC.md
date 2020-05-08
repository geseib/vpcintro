+++
title = "Create A VPC"
chapter = false
weight = 30
+++

## Creating a VPC

We now are ready to start our connectivity and routing policy.
Run CloudFormation template 2.tgw-csr.yaml to deploy the Transit Gateway, route Tables, and the Datacenter Router (Cisco CSR).

1. From the **Amazon VPC** console and from the left menu select **Your VPCs**.
    ![Your VPCs](/images/vpc-listvpcs.png)

1. Click the **Create VPC** button.

    ![VPC create](/images/vpc-create.png)

1. Name the **VPC** using a **Name tag**, such as **myVPC**. 
    - Enter **10.64.0.0/16** for the **IPv4 CIDR block**.
    - Leave **IPv6 CIDR block (no IPv6 CIDR block)**
    - Leave **Tenancy (Default)**.
    - Click the **Create** button at the bottom right.

    ![IGW Created](/images/vpc-created.png)
1. Click the **Close** button once the VPC has been created.
  
### You have completed the VPC Creation. ###