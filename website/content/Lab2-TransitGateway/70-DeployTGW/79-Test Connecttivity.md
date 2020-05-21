+++
title = "Test Connectivity"
chapter = false
weight = 79
+++

## Test connectivity across Transit Gateway

Now if we have complete all the steps we should be able to test connectivity across the TGW. We will be testing from the first EC2 instance that you created in VPC 10.64.0.0/16. It has an address of **10.64.2.10**. We will be pinging across the Transit Gateway to **10.65.2.10**

![test Connectivity](/images/tgw-test-diagram.png)
1. From the **Amazon EC2** console and from the left menu select **Instances**.

   ![connect button](/images/test2ndec2-list.png)

1. Check the box next to your instance in VPC64 and Click the **Connect** button aboe the list.

   ![connect session manager](/images/testec2-connect.png)

1. Click the radio button next to **Session Manager** and click the **Connect** button. _this will bring up a new browser tab with the Linux bash shell_

   ![ping test](/images/tgw-test-ping.png)

1. At the **sh-4.2\$** prompt,ping **10.65.2.10**.\_

   ```
   ping 10.65.2.10
   ```

   This will return something like the following

   ```
   sh-4.2$ ping 10.65.2.10
   PING 10.65.2.10 (10.65.2.10) 56(84) bytes of data.
   64 bytes from 10.65.2.10: icmp_seq=1 ttl=254 time=1.14 ms
   64 bytes from 10.65.2.10: icmp_seq=2 ttl=254 time=0.930 ms
   64 bytes from 10.65.2.10: icmp_seq=3 ttl=254 time=0.830 ms
   ^C
   --- 10.65.2.10 ping statistics ---
   3 packets transmitted, 3 received, 0% packet loss, time 2002ms
   rtt min/avg/max/mdev = 0.830/0.969/1.149/0.137 ms
   sh-4.2$
   ```


### Bonus - Can you solve this
There is a web server running on 10.65.2.10. You can also use **curl** and **curl 10.65.2.10**, but there is something missing in the Security group for the 10.65.2.10 EC2 instance. Can you figure it out?  __note: curl allows  us to see an http page in the bash shell. The web server is running on TCP port 80_

   ![ping test](/images/tgw-test-sg.png)

When completed you should see something like the following:
   ![ping test](/images/tgw-test-curl.png)



### Troubleshooting

If you are unable to ping across, go back and check the route tables. The most common issue is that the private route tables in the VPCs do not have the route to **10.0.0.0/8** pointing to the TGW. 


## You have completed the Lab.
