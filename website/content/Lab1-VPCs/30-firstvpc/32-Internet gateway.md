+++
title = "Create Internet Gateway"
chapter = false
weight = 32
+++

### Internet Gateway

An Internet Gateway is required to provide internet access to and from your VPC.
![Gateways Diagram](/images/creategateways-diagram.png)
    
1. From the **Amazon VPC** console and from the left menu select **Internet Gateways**.
   ![IGWS](/images/creategateways-igws.png)
    
1. Click the **Create Internet gateway** button.

   ![IGW create](/images/creategateways-createigw.png)
1. Name the **Internet Gateway** using a **Name tag**, such as **VPC64-IGW**. Click the **Create** button at the bottom right.

   ![IGW Created](/images/creategateways-igwcreated.png)
1. Click the **Close** button once the Internet Gateway has been created.

   ![IGW List](/images/creategateways-attachigwlist.png)
1. Check the box next to the newly create Internet Gateway, named **VPC64-IGW**. Click the Action button above the list, and select Attach to VPC.

   ![Attach IGW](/images/creategateways-attachigw.png)
1. Select your VPC from the list, and click the Attach button.

### You have completed the Internet Gateway Creation.
