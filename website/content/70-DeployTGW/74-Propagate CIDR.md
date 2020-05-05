+++
title = "Propagate VPC CIDR"
chapter = false
weight = 74
+++

### Propagate VPC CIDR to Route table

Propagating A VPC CIDR to a Transit Gateway route table, populates the Transit Gateway route table with a route to the VPC. You can propagate an Attachment to as many route tables as you need within the Transit Gateway.

We will repeat the process for VPC64 and VPC65 (_be sure to do both VPCs)


#### VPC 10.64.0.0/16 Propagation (First VPC)
1. From the **Amazon VPC** console and from the left menu select **Transit Gateway Route tables**.
   ![Route tables](/images/tgw-prop-list.png)

1. Click the **Action** button, and select **Create Propagation**.

   ![Propagation create](/images/tgw-prop-vpc64-create.png)

1. Create the **Propagation** by selecting the **VPC64** Attachment from the dropdown list.
    - Click the **Create Propagation** button.

    ![Propagation Created](/images/tgw-prop-vpc64-created.png)
1. Click the **Close** button once the TGW has been created.

#### VPC 10.65.0.0/16 Propagation (the other VPC!)
1. From the **Amazon VPC** console and from the left menu select **Transit Gateway Route tables**.
   ![Route tables](/images/tgw-prop-list.png)

1. Click the **Action** button, and select **Create Propagation**.

   ![Propagation create](/images/tgw-prop-vpc65-create.png)

1. Create the **Propagation** by selecting the **VPC65** Attachment from the dropdown list. (_it will be the one with an **Associated route table** listed_) )
    - Click the **Create Propagation** button.

    ![Propagation Created](/images/tgw-prop-vpc65-created.png)
1. Click the **Close** button once the TGW has been created.

#### Verify that routes are propagating


1. With the Route table selected from the list, you can click the **Propagations** tab in the details pane below the list. 

   ![Propagation](/images/tgw-rt-props.png)
1. you should see two VPC Attachments   

1. Now, click the **Routes** tab in the details pane below the list. 

   ![Routes](/images/tgw-rt-routes.png)
1. You should see two routes:
    - 10.64.0.0/16
    - 10.65.0.0/16

### You have completed the Transit Gateway Propagations.