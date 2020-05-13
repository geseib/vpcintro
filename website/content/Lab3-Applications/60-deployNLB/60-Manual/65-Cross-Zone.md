+++
title = "Cross-Zone Load Balancing"
chapter = false
weight = 65
+++

### Cross Zone Load Balancing


When you create a **internal Network Load Balancer**, you pick one subnets each in at least two Availability Zones. This creates a Elastic Network Interface with a private IP from those subnets. 

![Gateways Diagram](/images/nlb-cz-diagram.png)

### Step-by-step

   ![NLBs](/images/nlb-nlb-list.png)
1. From the **Amazon EC2** console and from the left menu, near the bottom, select **Load Balancers**. Check the box next to your **Network Load Balancer** in the list.

   ![Cross-Zone Disabled](/images/nlb-cz-before.png)

1. In the details panel below, review the current **Attributes**. In particular, that **Cross-Zone Load Balancing** is **Disabled**.

  ![Action](/images/nlb-cz-action.png)

1. From the **Action** menu above the list, select **Edit Attributes**.

  ![Edit Attributes](/images/nlb-cz-edit.png)
1. From the **Edit load balancer attributes** dialog, check the **Enable** box next for **Cross-Zone Load Balancing**. Then, click the **Save** button.


   ![Cross-Zone Enabled](/images/creategateways-ngwcreated.png)

1. Now go back and review the details panel below, review the current **Attributes**. In particular, that **Cross-Zone Load Balancing** is now **Enabled**.

### You have completed the Cross-Zone Load Balancing.
