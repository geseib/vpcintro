+++
title = "Test Connectivity"
chapter = false
weight = 52
+++

## Test from new EC2 Instance to the internet
It will take a few minutes for the Cloudformation template to to finish launching all of the resources.


1. From the **Amazon EC2** console and from the left menu select **Instances**.

    ![connect button](/images/testec2-list.png)
1. Check the box next to the new instance in the list and Click the **Connect** button aboe the list.

    ![connect session manager](/images/testec2-connect.png)
1. Click the radio button next to  **Session Manager** and click the **Connect** button. _this will bring up a new browser tab with the Linux bash shell_

    ![ping test](/images/testec2-ping.png)
1. At the **sh-4.2$** prompt, ping **www.example.com**. _press **CTRL-C** or **Command-C** to stop the ping._
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
    1. We can determine what public IP address you are using to get to the internet resource by the following command:
    ```
    dig +short myip.opendns.com @resolver1.opendns.com
    ```
    That will return something like:
    ```
    h-4.2$ dig +short myip.opendns.com @resolver1.opendns.com
    54.85.184.24
    ```

    You can also try the following:
    ```
    curl www.example.com
    ping www.amazon.com
    ```

### Troubleshooting ###

If you have any issues, it likely shows up with the fact that you cannot connect to the Ec2 Instance. See if you can troubleshoot it yourself, walking through the steps.

The following are good places to start: 
There are several steps that could be causing the issue.

1. Is the ec2 Instance in a **Private** subnet?
1. Is the IAM role you created attached to the EC2 instance
1. Does the IAM role have the **AmazonSSMManagedInstanceCore**
1. Are the correct route tables attached the subnets (Public route table to both public subnets and the PRivate route table to the Private subnets)
1. Did you add the 0.0.0.0/0 route to the IGW on the public route table and the 0.0.0.0/0 route to the NGW on the private route table. 


## You have completed the Lab.
