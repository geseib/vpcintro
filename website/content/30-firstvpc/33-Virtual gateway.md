+++
title = "Create Virtual Gateway"
chapter = false
weight = 33
+++


### Virtual Gateway ###
A Virtual Gateway is used to provide private access to your data center and other locations using a VPN or AWS DIrect Connect (a dedicated connection). We will set one up in assuming we will connect a datacenter.
![Gateways Diagram](/images/creategateways-diagram.png)

1. From the **Amazon VPC** console and from the left menu select **Virtual Gateways**.
    ![IGWS](/images/creategateways-vgws.png)

1. Click the Create **Virtual Gateway** button.

    ![IGW create](/images/creategateways-createvgw.png)

1. Name the **Virtual Gateway** using a **Name tag**, such as **myVPC-VGW**. Click the **Create** button at the bottom right.

    ![VGW Created](/images/creategateways-vgwcreated.png)
1. Click the **Close** button once the Virtual Gateway has been created.

    ![VGW List](/images/creategateways-attachvgwlist.png)
1. Click the Action button above the list, and select Attach to VPC.

    ![Attach VGW](/images/creategateways-attachvgw.png)
1. Select your VPC from the list, and click the Attach button.

### You have completed the Virutal Gateway Creationion. ###