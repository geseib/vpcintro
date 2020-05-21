+++
title = "Create Network Load Balancer"
chapter = false
weight = 64
+++

### Network Load Balancer

[Network Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/introduction.html) A functions at the fourth layer of the Open Systems Interconnection (OSI) model. It can handle millions of requests per second. 

  ![NLBs](/images/nlb-nlbs.png)
1. From the **Amazon EC2** console and from the left menu, near the bottom, select **Load Balancers**. Click the **Create Load Balancer** button.

   ![Select NLB](/images/nlb-select.png)

1. Click the Center **Create** button for the **Network Load Balancer**.

   ![create NLB](/images/nlb-config.png)
1. Create an **Network Load Balancer** with the following:
   - **Name**: name it, like **VPC65-NLB-Internal**.
   - Change the **Schema** to **internal**. _It will only get private IPs.
   - Leave the Liseners at default: **TCP**: and Port **80**.
   - **VPC**: select the myvpc2-VPC **10.65.0.0/16** from the dropdown list.
   - **Subnet**: Check both **Availability Zones** and Select both of the private subnets **VPC65-PrivateA** and **VPC65-PrivateB**.
   - Click the **Next Confgiure Security Settings**

   ![Security](/images/nlb-security.png)
1. If you were using TLS, this is where you would configure the Certificate and Security policy (which defines which TLS protocols and SSL Ciphers are allowed). For the lab, we are using HTTP. Click the **Next: Configure Routing**. 

   ![Routing](/images/nlb-routing.png)
1. **Configure Routing** with the following:
   - For **Target Group** select **Existing target group**. _if this is not an option then your target group is not configured correctly. Check to make sure you used **TCP** for the protocol and the correct **VPC** for your target group and then rteturn back to the **Create Network Load Balancer step**.
   - **Name**: select your **Target group** from the dropdown list.
   - **Health checks**: Keep as **HTTP** for the **Protocol** and **/** for the **Path**.
   - Click the **Next: Register Targets** button.



   ## You have created the Network Load Balancer.