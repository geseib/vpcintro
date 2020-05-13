+++
title = "Create Security Groups"
chapter = false
weight = 60
+++

## Create Security Groups

Security groups act as virtual statefull firewall for your instances to control inbound and outbound traffic. We will be adding a security group to our Launch instance to allow auto scaling EC2 instances to allow traffic on TCP port 80, for http.

   ![Security Group](/images/nlb-sg-list.png)
1. From the **Amazon EC2** console and from the left menu, mid-way down, select **Security Groups**. Click the **Create security group** button.

   ![connect button](/images/nlb-sg.png)

1. Configure the Security Group with the following settings:
   - **Security Group Name**: name it, like **VPC65-NLB-EC2**
   - **Description**: give it a description.
   - **VPC**: Select the 2nd VPC (10.65.0.0/8) from the dropdown list.

   ![connect button](/images/nlb-sg-rule.png)
1. Scroll down to **Inbound rules** and click the **Add rule** button and enter the following rule:
   - **Type**: **http**
   - **Source**: Keep **Custom** and enter **10.0.0.0/8**.
   - Click the **Create security group** button. _there is already an **Outbound rule** for all traffic._



### You have created the Security Group.
