+++
title = "Create Private routing"
chapter = false
weight = 36
+++

## Create a Private route table

We now are ready to define our next routing policy. This time for the private subnets.

![Route tables Diagram](/images/routetables-diagram.png)
1. From the **Amazon VPC** console and from the left menu select **Route tables**.
    ![Route tables](/images/routetables-private-list.png)

1. Click the Create **Route table** button.

    ![create Route table](/images/routetable-createprivate.png)

1. Name the **Route table** using a **Name tag**, such as **VPC64-Private Route Table**. and Select your VPC in the **VPC** dropdown list. Click the **Create button**.

    ![Route table Created](/images/routetable-created.png)
1. Click the **Close** button once the Route Table has been created. 

    ![Edit Route table](/images/routetables-editroutesprivate.png)
1. From the Route tables list in the console, check the box next to the **VPC64-Private Route Table**, click the **Action** button above the list, and select **Edit routes**.

    ![Add Default Route](/images/routetables-defaultrouteprivate.png)
1. Click the **Add** route button.
    - For **Destination**, enter: **0.0.0.0/0**
    - For **Target**, select **NAT Gateway** and pick your IGW from the list. (it will have an id like nat-002adb32dge312)
    - Click the **Save routes** button at the bottom right.

1. Click the **Close** button once the Route table has been edited.

    ![Associate Route Table](/images/routetables-associateprivatelist.png)
1. Check the box next to the **VPC64-Private Route table** in the List.
Click the **Action** button above the list, and select **Edit subnet associations**.

    ![Associate Route Table](/images/routetables-associateprivatesubnets.png)
1. Check the box next to the **PrivateA** and **PrivateB** subnets in the List. Click the **Save** button.

### You have completed the Private Route table. ###
    




