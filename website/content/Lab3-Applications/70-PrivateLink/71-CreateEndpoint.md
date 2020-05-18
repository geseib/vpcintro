+++
title = "Create VPC Endpoint"
chapter = false
weight = 71
+++

## Create VPC Endpoint
We will now create a VPC Endpoint in the **10.64.0.0/16** VPC to connect to our **Endpoint Service** we just created. This will create Elastic Network Interfaces in a subnet of each Availability Zone we have subnets for this VPC. 
_Remember the VPC Endpoints are created in the VPC that will consume (or use) the application_.

![Endpoint Service](/images/pl-vpce-diagram.png)

### Step-by-step



#### Security Group for Endpoint
   ![Security Group](/images/nlb-sg-list.png)
1. From the **Amazon EC2** console and from the left menu, mid-way down, select **Security Groups**. Click the **Create security group** button.

   ![connect button](/images/pl-vpce-sg-basic.png)

1. Configure the Security Group with the following settings:
   - **Security Group Name**: name it, like **VPC64-VPCE-SG**
   - **Description**: give it a description.
   - **VPC**: Select the 1st VPC (10.64.0.0/8) from the dropdown list.

   ![connect button](/images/pl-vpce-sg-rules.png)
1. Scroll down to **Inbound rules** and click the **Add rule** button and enter the following rule:
   - **Type**: **http**
   - **Source**: Keep **Custom** and enter **10.64.0.0/16**. _you could also try using the Security Group ID of your EC2 instance in the 10.64.0.0/16 VPC_.
   - Click the **Create security group** button. _there is already an **Outbound rule** for all traffic._


#### Record Endpoint Service Name 
_(if not completed previously)_
1. From the **Amazon VPC** console and from the left menu, near the bottom, select **Endpoint Services**. Check the box next to your **Endpoint Service** in the list.

   ![Select Endpoint Service](/images/pl-vpces-details.png)

1. In the details panel below, get the Service Name of the **Endpoint Service**. You can click the copy button to the right of the Service name.

#### Endpoint creation
![PL Console](/images/pl-vpce-list.png)

1. From the **Amazon VPC** console and from the left menu select **Endpoint**. Click the **Create Endpoint** button.

    ![Create Endpoint](/images/pl-vpce-create.png)

1. Configure the **VPC Endpoint** with the following selections:
    - For **Service Catagory** select **Find service by name**.
    - For the **Service Name** Paste in the **Endpoint Service** name recorded above _(or in previous task)_ It will look something like this: **com.amazonaws.vpce.us-east-1.vpce-svc-0a37cf83d4fd5876c**.
    - Click the **Verify** button. You should see **Service name found.** Otherwise, you back and make sure you recorded the correct name.

       ![Create Endpoint](/images/pl-vpce-create-vpc.png)

1. Scroll down and Configure the **VPC Endpoint** with the following selections:
    - For **VPC** select the 10.64.0.0/16 VPC from the dropdown list.
    - This should bring up the two Availability zones already checked. Change the **Subnet ID**s to the private subnets. _no need to put these endpoints in public subnets, since they are just for this VPC_. 
    
       ![Create Endpoint](/images/pl-vpce-create-sgtag.png)

1. Scroll down again and Configure the **VPC Endpoint** with the following selections:
    - For **Security Group** select the security group you created above.
    - Click **new tag** button
        - **Key**: Type **Name** _use upper case 'N', as its case sensitive_
        - **Vaule**: Name your VPC Endpoint something like **VPC64-VPCEtoVPC65-NLB**
    - Click the **Create endpoint** in the bottom right.
    


    ![Endpoint Created](/images/pl-vpce-created.png)

1. Click the **Close** button once the **Endpoint ** has been created.

### Take a look at the Endpoint details and record the DNS name

   ![Endpoint Details](/images/pl-vpce-created.png)
1. 


### You have completed the Create VPC Endpoint .
