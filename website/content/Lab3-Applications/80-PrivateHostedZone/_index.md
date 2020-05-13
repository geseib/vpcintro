+++
menutitle = "Private Hosted Zone"
chapter = false
weight = 70
+++

## Private Hosted Zone

Now lets simplify finding our applications by using Route 53 Private Hosted Zones. 


![TGW Diagram](images/tgw-diagram.png)

#### We will complete the following steps:
1. Create a Transit Gateway

1. Create a Transit Gateway route table

1. Attach both VPCs to the Transit Gateway

1. Associate both VPCs to the Transit Gateway route table

1. Propagate both VPCs to the Transit Gateway route table

1. Edit the Private Subnet route tables for both VPCs

1. Test connectivity between VPCs

