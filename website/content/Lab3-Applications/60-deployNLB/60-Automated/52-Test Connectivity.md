+++
title = "Test Connectivity"
chapter = false
weight = 52
+++

## Test connectivity from the Same VPC or across the TGW

  ![NLBs](/images/nlb-test-diagram.png)

You can test from either on the EC2 instance **10.64.2.10** _(light blue line)_ or **10.65.2.10** _(light red line)_.

###Step-by-step
First let's get the DNS name of the **Network Load Balancer**

  ![NLBs](/images/nlb-nlb-list.png)
1. From the **Amazon EC2** console and from the left menu, near the bottom, select **Load Balancers**. Check the box next to your **Network Load Balancer** in the list.

   ![Select NLB](/images/nlb-details.png)

1. In the details panel below, get the DNS Name of the load balancer. You can click the copy button to the right of the DNS name.


1. From the **Amazon EC2** console and from the left menu select **Instances**.

   ![connect button](/images/testec2-list.png)

1. Check the box next to your instance in the list and Click the **Connect** button above the list.

   ![connect session manager](/images/testec2-connect.png)

1. Click the radio button next to **Session Manager** and click the **Connect** button. _this will bring up a new browser tab with the Linux bash shell_

   ![ping test](/images/testec2-ping.png)

1. At the **sh-4.2\$** prompt,curl **vpc65.example.aws**.\_

   ```
   curl VPC65-NLB-Internal-xxxxxxxx.elb.us-east-1.amazonaws.com
   ```

   This will return something like the following

   ```
   h-4.2$ curl VPC65-NLB-Internal-b5d244bcb071a9be.elb.us-east-1.amazonaws.com
   Welcome to my web server. Server private IP is 10.65.2.178
   Availability Zone: us-east-1a
   MY Web Server Demo
   remote ip is 10.64.2.10
   remote tcp port is 46254
   ```

## You have completed the Lab.
