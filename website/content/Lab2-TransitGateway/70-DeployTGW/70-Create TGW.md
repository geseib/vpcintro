+++
title = "Create Transit Gateway"
chapter = false
weight = 70
+++

## Create Transit Gateway

We will use a Transit Gateway to route between the two VPCs. Lets create the Transit Gateway now.


![TGW Console](/images/tgw-list.png)

1. From the **Amazon VPC** console and from the left menu scroll down and select **Transit Gateways**. Click the **Create Transit Gateway** button.

    ![Create TGW](/images/tgw-create.png)

1. Configure the **Transit Gateway** with the following selections:
    - **Name tag**: give the Transit Gateway a name, such as **myTGW**.
    - **Description**: give the Transit Gateway a description, such as **First TGW**
    - **Amazon side ASN**: enter **65000** _best practice for TGWs that you want to peer: set a unique ASN between TGWs_
    - **DNS support**: checked
    - **VPN ECMP support**: checked
    - **Default route table association**: **UN**checked
    - **Default route table propagation**: **UN**checked
    - **Multicast support**(_if avail in your region_): **UN**checked
    - **Auto accept shared attachments**: **check**
    - Click the **Create Transit Gateway** button.

    _Be sure to uncheck the Default route table association and propagation. We do this becuase we want to control what route table each attachment uses, and which atachments advertise routes to the route tables in the Transit Gateway._

    -The Auto accept shared attachments option lets those AWS accounts we have shared the TGW with, to create an attachment to this Transit Gateway. They still wont be able to route without action on our end, becuase we unchecked the router table association/propagation._

    ![TGW Created](/images/tgw-created.png)

1. Click the **Close** button once the TGW has been created.


### You have completed the Create TGW.
