+++
title = "Create Private Hosted Zone"
chapter = false
weight = 80
+++

## Create a Private Hosted Zone

We will use a Route 53 Private Hosted Zone to use more meaningful and flexible DNS names for our application. This will allow us to make changes to our application without requiring the consumers of our application to point to a new IP address or DNS host name. 

### Step-by-step
_note, if this is an AWS Event you may see errors stating you dont have sufficent permissions. This is expected becuase of restrictions to access like Domain Reginstration. Lab will work fine._

#### First let's get the DNS name of the **Network Load Balancer**

  ![NLBs](/images/nlb-nlb-list.png)
1. From the **Amazon EC2** console and from the left menu, near the bottom, select **Load Balancers**. Check the box next to your **Network Load Balancer** in the list.

   ![Select NLB](/images/nlb-details.png)

1. In the details panel below, get the DNS Name of the load balancer. You can click the copy button to the right of the DNS name. Paste it to a scratch doc on your computer to use later.

#### Create the Hosted Zone

   ![Hosted Zones](/images/r53-welcome.png)
1. From the **Route53** console and from the left menu select **Hosted Zones**. Click the **Create Hosted Zones** button.

   ![Create button](/images/r53-empty.png)

1. From the Hosted Zones list, again Click the **Create Hosted Zone** button above the list.

    ![Create PHZ](/images/r53-phz-create.png)
1. Configure the **Hosted Zone** with the following selections:
    - **Domain Name**: give the zone a name, such as **awslab.internal**.
    - **Comment**: give the zone a description, such as **VPC Intro PHZ lab**
    - **Type**: select **Private Hosted Zone for Amazon VPC** from the dropdown list. _Private hosted zones are only visable with the VPCs that are associated with the zone._
    - **VPC ID**: select the **10.65.0.0/16** VPC from the dropdown list

    - Click the **Create ** button.

    ![Associate PHZ](/images/r53-phz-associate.png)
1.  From the **Route53** console and from the left menu select **Hosted Zones**. Check the box net to the **awslab.internal** zone and modify the zone info to the right.
    
    - **VPC ID**: select the **10.64.0.0/16** VPC from the dropdown list

    - Click the **Associate New VPC** button.


### Create recordsets
We will be using Alias records. Alias records recursively lookup DNS records at the server and return the final results. It is similar to CNAME records, however, with CNAME, the DNS client has to get each query and then do the follow upcurl l recursive query back to the server until its get to the IP address answer.

1. From the **awslab.internal** Hosted Zones , Click the **Create Record Set** button above the list.

1. Complete the new **Record Set** with the following:
    - **Name**: **global**. it will complete as global.awslab.internal.
    - **Type**: leave as **A - IPv4 address**
    - **Alias**: select **Yes**
    - **Alias Target**: Either paste in the DNS name for the Network Load Balancer or select it from the dropdown list.
    - **Routing Policy**: leave as **Simple** _other option would make sense if we were deploying another NLB in either in this region or another region and we wanted to split the load or have failover between them_
    - Click the **Create** button in the bottom right.

1. Create another Record Set by clicking the **Create Record Set** button above the list again. Complete the new **Record Set** with the following:
    - **Name**: **local**. it will complete as global.awslab.internal.
    - **Type**: leave as **A - IPv4 address**
    - **Alias**: select **Yes**
    - **Alias Target**: type in **global.awslab.internal**. _this will reference the **Record Set** created above._
    - **Routing Policy**: leave as **Simple** 
    - Click the **Create** button in the bottom right.


### You have completed the Create Private Hosted Zone.
