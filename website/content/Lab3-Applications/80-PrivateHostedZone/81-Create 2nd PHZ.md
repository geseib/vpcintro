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

    ![Create PHZ](/images/r53-create2nd.png)
1. Configure the **Hosted Zone** with the following selections:
    - **Domain Name**: give the zone the same name as the previous zone but with **local.** infornt of it, such as **local.awslab.internal**.
    - **Comment**: give the zone a description, such as **VPC Intro PHZ labW**
    - **Type**: select **Private Hosted Zone for Amazon VPC** from the dropdown list. _Private hosted zones are only visable with the VPCs that are associated with the zone._
    - **VPC ID**: select the **10.64.0.0/16** VPC from the dropdown list

    - Click the **Create ** button.

    ![Create PHZ](/images/r53-createVPCE.png)
### Create recordsets
We will be using Alias records. Alias records recursively lookup DNS records at the server and return the final results. It is similar to CNAME records, however, with CNAME, the DNS client has to get each query and then do the follow up recursive query back to the server until its get to the IP address answer.

1. From the **local.awslab.internal** Hosted Zones , Click the **Create Record Set** button above the list.

1. Create another Record Set by clicking the **Create Record Set** button above the list again. Complete the new **Record Set** with the following:
    - **Name**: Leave blank. It will complete as local.awslab.internal.
    - **Type**: leave as **A - IPv4 address**
    - **Alias**: select **Yes**
    - **Alias Target**: select or type in the VPC Endpoint DNS name. In the dropdown list there will be three DNS names for the VPC Endpoint you created: 1 returns all IP across all Availability Zones that the VPC endpoint was deployed to, The others only return 1 Address for a single Availability Zone._
    - **Routing Policy**: leave as **Simple** 
    - Click the **Create** button in the bottom right.


## You have completed the Route Table creation.

