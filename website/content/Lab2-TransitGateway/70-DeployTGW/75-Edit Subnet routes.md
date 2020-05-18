+++
title = "Edit VPC Route tables"
chapter = false
weight = 75
+++

### Edit VPC Private Route tables

We need to define when traffic gets routed to our Transit Gateway from each VPC subnet. In our case, we want all RFC 1918 10.0.0.0/8 traffic to be routed to the Transit Gateway. We will let the Transit Gateway provide more detailed routing. 

We will repeat the process for VPC64 and VPC65 (_be sure to do both VPCs)


#### VPC64 Private Route table (First VPC)
1. From the **Amazon VPC** console and from the left menu select **Route tables** (_it will be near the top of the list_).
   ![Route tables](/images/tgw-vpc-rt-vpc64-list.png)

1. Check the box next to the Private route table for 10.64.0.0/16 subnet (named like **VPC64-Private route table**)

1. Click the **Action** button, and select **Edit routes**.

   ![Edit Route](/images/tgw-vpc-rt-vpc64-edit.png)

1. Click the **Add routes** botton, at the bottom of the route list. 
   - Enter **10.0.0.0/8** for the destination
   - For the **Target** select **Transit Gateway** from the dropdown list and pick your **TGW** (_it will have an id like tgw-0700a345567b23f0_)
   - Click the **Save Route** button.

    ![Route edited](/images/tgw-vpc-rt-edited.png)
1. Click the **Close** button once the route table has been edited.

#### VPC65 Private Route table (the other VPC!)
1. From the **Amazon VPC** console and from the left menu select **Route tables** (_it will be near the top of the list_).
   ![Route tables](/images/tgw-vpc-rt-vpc65-list.png)

1. Check the box next to the Private route table for 10.65.0.0/16 subnet (named like **VPC65-Private route table**)

1. Click the **Action** button, and select **Edit routes**.

   ![Edit Route](/images/tgw-vpc-rt-vpc65-edit.png)

1. Click the **Add routes** botton, at the bottom of the route list. 
   - Enter **10.0.0.0/8** for the destination
   - For the **Target** select **Transit Gateway** from the dropdown list and pick your **TGW** (_it will have an id like tgw-0700a345567b23f0_)
   - Click the **Save Route** button.

    ![Route edited](/images/tgw-vpc-rt-edited.png)
1. Click the **Close** button once the route table has been edited.

_Notice how we didnt modify the **Public** VPC route tables. In our scenario, we dont need for the public to route to anything beyond the VPC. So in order to prevent that access, we provided no route to the Transit gateway in the public route tables._

### You have completed the Subnet Route editing.