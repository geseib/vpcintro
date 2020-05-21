+++
menutitle = "Option 1. Manual"
chapter = false
weight = 61
+++

## Manually Create a Network Load Balancer and Autoscaling Group

Lets depoly a Network Load Balancer backed by an Autoscaling group. If you would rather go quickly to the next lab and have cloudformation build the application to share, you can use the [Option 2. Cloudformation](../lab3-applications/60-deploynlb/60-automated.html)

Make sure you are logged into your AWS account (Either your AWS account or via the AWS Event Dashboard if an AWS hosted event).

![NLB Diagram](/images/nlb-diagram.png)


Verify that you have access to the **EC2** Instance in the 2nd VPC. it should be named **VPC65-Webserver**

<details>
<summary>Step-by-step instructions</summary>
<p>

1. From the **Amazon EC2** console and from the left menu select **Instances**.

   ![connect button](/images/testec2-list.png)

1. Check the box next to the **VPC65-Webserver** instance in the list and Click the **Connect** button above the list.

   ![connect session manager](/images/testec2-connect.png)

1. Click the radio button next to **Session Manager** and click the **Connect** button. _this will bring up a new browser tab with the Linux bash shell_

   ![ping test](/images/testec2-ping.png)

1. At the **sh-4.2\$** prompt, ping **www.example.com**. _press **CTRL-C** or **Command-C** to stop the ping._
   ```
   ping www.example.com
   ```
   This will return something like the following
   ```
   PING www.example.com (93.184.216.34) 56(84) bytes of data.
   64 bytes from 93.184.216.34 (93.184.216.34): icmp_seq=1 ttl=52 time=1.55 ms
   64 bytes from 93.184.216.34 (93.184.216.34): icmp_seq=2 ttl=52 time=0.939 ms
   64 bytes from 93.184.216.34 (93.184.216.34): icmp_seq=3 ttl=52 time=0.814 ms
   ^C
   --- www.example.com ping statistics ---
   3 packets transmitted, 3 received, 0% packet loss, time 2003ms
   rtt min/avg/max/mdev = 0.814/1.102/1.555/0.326 ms
   ```
   
</p>
</details>
