+++
title = "Create Route table"
chapter = false
weight = 71
+++

## Create Transit Gateway Route table
We can have multiple route tables in our Transit Gateway. Route tables define routing behaviors not domains. In other words, just becuase two VPC use the same route table, they will not nessasarily be able to route to each other. However, in this demo we want to allow the two VPCs to route to each other.

   ![TGW Route tables](/images/tgw-rt-list.png)
1. From the **Amazon VPC** console and from the left menu select **Transit Gateway Route tables**. Click **Create Transit Gateway Route Table**.

   ![Create TGW Route table](/images/tgw-rt-create.png)
1. Give the route table a name, such as **Dev route table** and **Select the Transit Gateway ID** from the dropdown list for your TGW. Click the **Create Transit Gateway Route Table** button at the bottom right.

   ![TGW Route table created](/images/tgw-rt-created.png)
1. Click the **Close** button once the TGW route table has been created.

## You have completed the Route Table creation.

