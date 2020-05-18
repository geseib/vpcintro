+++
title = "Creae Second Private Hosted Zone"
chapter = false
weight = 81
+++
   
## Create 2nd Private Hosted Zone
We could use the Current Private Hosted Zone and use the Transit Gateway to get to our Application. Or we could use the PrivateLink that we setup eariler. _In the real world, we likely wouldnt provide both paths (Transit Gateway and PrivateLink to the same application, but this lets us see the difference)_ 

#### Create the Hosted Zone

   ![Hosted Zones](/images/r53.png)
1. From the **Route53** console and from the left menu select **Hosted Zones**. Click the **Create Hosted Zones** button.

   ![Create button](/images/r53-list.png)

1. From the Hosted Zones list, again Click the **Create Hosted Zone** button above the list.

    ![Create PHZ](/images/r53-create.png)
1. Configure the **Hosted Zone** with the following selections:
    - **Domain Name**: give the zone a name, such as **awslab.internal**.
    - **Comment**: give the zone a description, such as **VPC Intro PHZ labW**
    - **Type**: select **Private Hosted ZOne for AMazon VPC** from the dropdown list. _Private hosted zones are only visable with the VPCs that are associated with the zone._
    - **VPC ID**: select the **10.65.0.0/16** VPC from the dropdown list

    - Click the **Create ** button.

    ![ZOne Created](/images/tgw-created.png)
1. Click the **Close** button once the TGW has been created.


### Create recordsets
We will be using Alias records. Alias records recursively lookup DNS records at the server and return the final results. It is similar to CNAME records, however, with CNAME, the DNS client has to get each query and then do the follow up recursive query back to the server until its get to the IP address answer.

1. From the **awslab.internal** Hosted Zones , Click the **Create Record Set** button above the list.

1. Complete the new **Record Set** with the following:
    - **Name**: **global**. it will complete as global.awslab.internal.
    - **Type**: leave as **A - IPv4 address**
    - **Alias**: select **Yes**
    - **Alias Target**: Either past in the DNS name for the Network Load Balancer or select it from the dropdown list.
    - **Routing Policy**: leave as **Simple** _other option would make sense if we were deploying another NLB in either in this region or another region and we wanted to split the load or have failover between them_
    - Click the **Create** button in the bottom right.

1. Create another Record Set by clicking the **Create Record Set** button above the list again. Complete the new **Record Set** with the following:
    - **Name**: **local**. it will complete as global.awslab.internal.
    - **Type**: leave as **A - IPv4 address**
    - **Alias**: select **Yes**
    - **Alias Target**: type in **global.awslab.internal**. _this will reference the **Record Set** created above._
    - **Routing Policy**: leave as **Simple** 
    - Click the **Create** button in the bottom right.


## You have completed the Route Table creation.

