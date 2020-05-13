+++
title = "Create NAT Gateway"
chapter = false
weight = 34
+++


### NAT Gateway ###
A NAT Gateway provides outbound internet access to private resources in our VPC. We will need this to connect to and be able to install packages on our EC2 instance later. 
![Gateways Diagram](/images/creategateways-diagram.png)

1. From the **Amazon VPC** console and from the left menu select **NAT Gateways**.
    ![NGWs](/images/creategateways-ngws.png)

1. Click the Create **NAT Gateway** button.

    ![NGW create](/images/creategateways-createngw.png)

1. Create the **NAT Gateway** using the bellow steps. Click the **Create** button at the bottom right, when you are done.
    - Select the ”PublicA” subnet from the **Subnet** dropdown list.
    - Click the **Allocate Elastic IP address** button to automatically create and fill the **Elastic IP Allocation ID**.
    - _Optional:Add a Tag with the Key – **Name**, and a Value such as **VPC64-NATGW**_

    ![NGW Created](/images/creategateways-ngwcreated.png)
1. Click the **Close** button once the NAT Gateway has been created. _We will edit the route tables later._

### You have completed the NAT Gateway Creation. ###