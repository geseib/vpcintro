+++
title = "Create Public routing"
chapter = false
weight = 35
+++

## Create a Public route table

We now are ready to define our routing policy. While there is a Main route table that all subnets are currently associated with, we are going to create route tables for each of our tiers: public and private. Let's start with the public route table...

![Route tables Diagram](/images/routetables-diagram.png)
1. From the **Amazon VPC** console and from the left menu select **Route Tables**.
    ![Route tables](/images/routetables-list.png)

1. Click the Create **Route table** button.

    ![create Route table](/images/routetable-create.png)

1. Name the **Route table** using a **Name tag**, such as **VPC64-Public Route Table**. and Select your VPC in the **VPC** dropdown list. Click the **Create button**.

    ![Route table Created](/images/routetable-created.png)
1. Click the **Close** button once the Route Table has been created. 

    ![Edit Route table](/images/routetables-editroutespublic.png)
1. From the Route tables list in the console, check the box next to the **VPC64-Public Route table**, click the **Action** button above the list, and select **Edit routes**.

    ![Add Default Route](/images/routetables-defaultroutepubic.png)
1. Click the **Add** route button.
    - For **Destination**, enter: **0.0.0.0/0**
    - For **Target**, select **Internet Gateway** and pick your IGW from the list. (it will have an id like igw-002adb32dge312)
    - Click the **Save routes** button at the bottom right.
    + _note: 0.0.0.0/0 is called the default route. It means: use this route when there is no more specific destination in the list that matches. In this case send it out toward the internet._

1. Click the **Close** button once the Route table has been edited.

    ![Associate Route Table](/images/routetables-associatepubliclist.png)
1. Check the box next to the **VPC64-Public Route table** in the List.
Click the **Action** button above the list, and select **Edit subnet associations**.

    ![Associate Route Table](/images/routetables-associatepublicsubnets.png)
1. Check the box next to the **PublicA** and **PublicB** subnets in the List. Click the **Save** button.


### You have completed the Public Route table. ###


