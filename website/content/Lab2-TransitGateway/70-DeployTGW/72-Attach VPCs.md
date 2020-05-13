+++
title = "Attach VPCs"
chapter = false
weight = 72
+++

### Attach VPCs

An Transit Gateway VPC Attachment needs to place an ENI into each Availability Zone that you use in your VPC. You will be placing them in the **PrivateA** and **PrivateB** subnets.
![Gateways Diagram](/images/tgw-att-diagram.png)

We will repeat the process for VPC64 and VPC65 (_be sure to do both VPCs_)


#### VPC 10.64.0.0/16 Attachment (First VPC)
1. From the **Amazon VPC** console and from the left menu select **Transit Gateway Attachments**.
   ![Attachments](/images/tgw-att-vpc64-list.png)

1. Click the **Create Transit Gateway Attachment** button.

   ![Attachment create](/images/tgw-att-vpc64-create.png)

1. Configure the **Transit Gateway Attachment** with the following selections:
    - **Transit Gateway ID**: select your TGW from the dropdown list.
    - **Attachment tpye**: leave as **VPC**.
    - **Attachment name tag**: enter a name, such as **VPC64**
    - **DNS support**: leave checked
    - **IPv6**: leave unchecked
    - **VPC ID**: select VPC with **10.64.0.0/16** from the list
    - **Subnet IDs**:
       - **us-east-1a**: select the **VPC64-PrivateA subnet** from the dropdown list
       - **us-east-1b**: select the **VPC64-PrivateB subnet** from the dropdown list
    - Click the **Create attachment** button.

    _Be sure you selected the Private subnets for both Availability Zones_

    ![Attachment Created](/images/tgw-att-vpc65-created.png)
1. Click the **Close** button once the TGW has been created.

#### VPC 10.65.0.0/16 Attachment (the other VPC!)
1. From the **Amazon VPC** console and from the left menu select **Transit Gateway Attachments**.
   ![Attachments](/images/tgw-att-vpc65-list.png)

1. Click the **Create Transit Gateway Attachment** button.

   ![Attachment create](/images/tgw-att-vpc65-create.png)

1. Configure the **Transit Gateway Attachment** with the following selections:
    - **Transit Gateway ID**: select your TGW from the dropdown list.
    - **Attachment tpye**: leave as **VPC**.
    - **Attachment name tag**: enter a name, such as **VPC65**
    - **DNS support**: leave checked
    - **IPv6**: leave unchecked
    - **VPC ID**: select VPC with **10.65.0.0/16** from the list
    - **Subnet IDs**:
       - **us-east-1a**: select the **VPC65-PrivateA subnet** from the dropdown list
       - **us-east-1b**: select the **VPC65-PrivateB subnet** from the dropdown list
    - Click the **Create attachment** button.

    _Be sure you selected the Private subnets for both Availability Zones_

    ![Attachment Created](/images/tgw-att-vpc65-created.png)
1. Click the **Close** button once the TGW has been created.

![Attachment Created](/images/tgw-att-verify.png)
Verify you have two attachments in the list. _They will have a **State** of **pending** for a few minutes until they are **available**. you may need to refresh by click the refresh icon above the table._


### You have completed the Transit Gateway Attachments._
