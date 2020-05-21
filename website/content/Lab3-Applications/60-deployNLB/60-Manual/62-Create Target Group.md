+++
title = "Create Target Group"
chapter = false
weight = 62
+++

### Create Taget Group

[Target groups](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-target-groups.html) is used to route requests to one or more registered targets. This is where our Auto scaling group will place EC2 instances created from our Launch template. The **Network Load Balancer** will send traffic to the Target group.

   ![target group](/images/nlb-tgs.png)
1. From the **Amazon EC2** console and from the left menu, near the bottom, select **Target groups**. Click the **Create Target group** button.

   ![basic config](/images/nlb-tg-basic.png)

1. Specify group details with the following **Basic Configuration**:
   - Leave the **Choose target type** as **Instances**.
   - **Target group name**: name it, like **basicwebservers**.
   - **Protocal and Port**: Change Protcol to **TCP** and Port to **80**.
   - **VPC**: select the VPC65 **10.65.0.0/16** from the dropdown list.


   ![health check](/images/nlb-tg-health.png)

1. Scroll down to **Health checks** and configure the following:
   - Change the health check to **HTTP** from the dropdown
   - Leave the **Health check path** set to **/**
   - click the **Next** button.

   ![register targets](/images/nlb-tg-register.png)
1. We will hold off on registering targets, as we will allow the auto scaling group to do that for us. Scroll down and click the **Create taget group** button.

## You have created the Target group.