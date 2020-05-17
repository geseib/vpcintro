+++
title = "Test Connectivity"
chapter = false
weight = 52
+++

## Test from new EC2 Instance to the internet
It will take a few minutes for the Cloudformation template to to finish launching all of the resources.


1. From the **Amazon EC2** console and from the left menu select **Instances**.

    ![connect button](/images/test2ndec2-list.png)
1. Check the box next to the new instance in the list (named VPC65-EC) and click the **Connect** button above the list.

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

If you have any issues, verify that the Cloudformation stack has complete. It can take a few minutes to finish the automation and the EC2 instance to finish booting up.


## You have completed the Lab.
