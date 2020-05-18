+++
title = "Create VPC Endpoint Service"
chapter = false
weight = 70
+++

## Create VPC Endpoint Service

We will create a VPC Endpoint Service to make our NLB application availabile to share to other VPCs in the same region. We could even share to VPCs in other AWS accounts. _Remember the VPC **Endpoint Services** are created in the VPC that will produce (or host) the application_.

![Endpoint Service](/images/pl-vpces-diagram.png)

### Step-by-step
![PL Console](/images/pl-list.png)

1. From the **Amazon VPC** console and from the left menu select **Endpoint Service**. Click the **Create Endpoint Service** button.

    ![Create VPCES](/images/pl-create-vpcse.png)

1. Configure the **VPC Endpoint Service** with the following selections:
    - **Associate Network Load Balancer**: check to box next to the NLB created earlier, named  **VPC65-NLB-Internal**.
    - Notice the **Included** and **Excluded Availability Zones**. when sharing to other accounts it is a good practice to place the NLB in all Availability Zones to provide complete access no matter which Availiablity Zones the consumer VPCs are in_.
    - Uncheck the **Require acceptance for endpoint**, so you do not have accept the VPC Endpoint when the consumer VPCs create them. 
    - Uncheck **Enable private DNS name**. _This is a great feature to automate creation of the DNS entry along with the Endpoint creation for the consumers. It requires proof of domain ownership. We dont have a real public DNS domain to use for the lab._
    - Click the **Add Tag**: button and give it a tag with the **Key** as **Name** and the **Value** as something like **VPC65-NLB-VPCES**
    - CLick the **Create service** button to finish


    ![VPCES Created](/images/pl-created-vpcse.png)

1. Click the **Close** button once the **Endpoint Service** has been created.

#### Verify and Record Endpoint Service Name

1. From the **Amazon VPC** console and from the left menu, near the bottom, select **Endpoint Services**. Check the box next to your **Endpoint Service** in the list.

   ![Select Endpoint Service](/images/pl-vpces-details.png)

1. In the details panel below, get the DNS Name of the **Endpoint Service****. You can click the copy button to the right of the Service name.



### You have completed the Create VPC Endpoint Service.
