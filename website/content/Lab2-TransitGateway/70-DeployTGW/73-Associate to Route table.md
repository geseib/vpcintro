+++
title = "Associate to Route table"
chapter = false
weight = 73
+++

### Associate VPCs to Route table

Associating A VPC Attachment to a Transit Gateway route table, tells the Transit Gateway which route table to use when traffic comes from this Attachment.

We will repeat the process for VPC64 and VPC65 (_be sure to do both VPCs)


#### VPC 10.64.0.0/16 Association (First VPC)
1. From the **Amazon VPC** console and from the left menu select **Transit Gateway Route tables**.
   ![Route tables](/images/tgw-assoc-list.png)

1. Click the **Action** button, and select **Create association**.

   ![Association create](/images/tgw-assoc-vpc64-create.png)

1. Create the **Association** by selecting the **VPC64** Attachment from the dropdown list.
    - Click the **Create association** button.
    - _if the **VPC64** attachment is not there, it may still be creating. Give it another minute or so_.

    ![Association Created](/images/tgw-assoc-vpc64-created.png)
1. Click the **Close** button once the TGW has been created.

#### VPC 10.65.0.0/16 Association (the other VPC!)
1. From the **Amazon VPC** console and from the left menu select **Transit Gateway Route tables**.
   ![Route tables](/images/tgw-assoc-list.png)

1. Click the **Action** button, and select **Create association**.

   ![Association create](/images/tgw-assoc-vpc65-create.png)

1. Create the **Association** by selecting the **VPC65** Attachment from the dropdown list. (_it will be the one with an **Associated route table** listed_) )
    - Click the **Create association** button.

    ![Association Created](/images/tgw-assoc-vpc65-created.png)
1. Click the **Close** button once the TGW has been created.

#### Verify that Attachments are associated


1. With the Route table selected from the list, you can click the **Associations** tab in the details pane below the list. 

   ![Association](/images/tgw-rt-assocs.png)
   _You should see two VPC Attachments_


### You have completed the Transit Gateway Associations.