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

   
    >VPC64 CIDR
    ```
    10.64.0.0/16
    ```
     

1. Name the **VPC** using a **Name tag**, such as **VPC64**. 
    - Enter **10.64.0.0/16** for the **IPv4 CIDR block**.
    - Leave **IPv6 CIDR block (no IPv6 CIDR block)**
    - Leave **Tenancy (Default)**.
    - Click the **Create** button at the bottom right.

    ![VPC Created](/images/vpc-created.png)
1. Click the **Close** button once the VPC has been created.

#### Enable DNS Hostnames
We want to be able to use Route53 **Private Hosted Zones** for DNS resolution, so lets go ahead and enable this, as it is a prerequisite.

![Enalbe Hostnames](/images/vpc-hostnames.png)

1. Check the box next to the new VPC, **VPC64**, in the list, click the **Actions** button and select **Enable DNS hostnames** from the list.

    ![Edit Hostnames](/images/vpc-hostnames-edit.png)

1. Check the box to **enable** **DNS hostnames** and click the **Save** button.

  
### You have completed the VPC Creation. ###