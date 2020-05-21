+++
title = "Test Connectivity"
chapter = false
weight = 89
+++

## Test connectivity across Transit Gateway

Now if we have completed all the steps, we should be able to test connectivity across the TGW. We will be testing from the first EC2 instance that you created in VPC 10.64.0.0/16. It has an address of **10.64.2.10**. We will be pinging across the Transit Gateway to **10.65.2.10**

 ![Test Diagram](/images/tgw-test-diagram.png)
1. From the **Amazon EC2** console and from the left menu select **Instances**.

   ![connect button](/images/test2ndec2-list.png)  

1. Check the box next to your instance in VPC64 and Click the **Connect** button aboe the list.

   ![connect session manager](/images/testec2-connect.png)

1. Click the radio button next to **Session Manager** and click the **Connect** button. _this will bring up a new browser tab with the Linux bash shell_

   ![ping test](/images/tgw-test-ping.png)

1. At the **sh-4.2\$** prompt,dig **local.awslab.internal**.\_

   ```
   dig local.awslab.internal
   ```

   This will return something like the following

   ```
   sh-4.2$ dig local.awslab.internal

   ; <<>> DiG 9.11.4-P2-RedHat-9.11.4-9.P2.amzn2.0.2 <<>> local.awslab.internal
   ;; global options: +cmd
   ;; Got answer:
   ;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 16867
   ;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1

   ;; OPT PSEUDOSECTION:
   ; EDNS: version: 0, flags:; udp: 4096
   ;; QUESTION SECTION:
   ;local.awslab.internal.         IN      A

   ;; ANSWER SECTION:
   local.awslab.internal.  17      IN      A       10.64.3.253
   local.awslab.internal.  17      IN      A       10.64.2.175

   ;; Query time: 0 msec
   ;; SERVER: 10.64.0.2#53(10.64.0.2)
   ;; WHEN: Mon May 18 03:06:36 UTC 2020
   ;; MSG SIZE  rcvd: 82
   ```

At the **sh-4.2\$** prompt,dig **global.awslab.internal**.\_

   ```
   dig global.awslab.internal
   ```

   This will return something like the following

   ```
   sh-4.2$ dig global.awslab.internal

   ; <<>> DiG 9.11.4-P2-RedHat-9.11.4-9.P2.amzn2.0.2 <<>> global.awslab.internal
   ;; global options: +cmd
   ;; Got answer:
   ;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 35296
   ;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1

   ;; OPT PSEUDOSECTION:
   ; EDNS: version: 0, flags:; udp: 4096
   ;; QUESTION SECTION:
   ;global.awslab.internal.                IN      A

   ;; ANSWER SECTION:
   global.awslab.internal. 58      IN      A       10.65.2.113
   global.awslab.internal. 58      IN      A       10.65.3.6

   ;; Query time: 0 msec
   ;; SERVER: 10.64.0.2#53(10.64.0.2)
   ;; WHEN: Mon May 18 03:06:26 UTC 2020
   ;; MSG SIZE  rcvd: 83

   ```
1. How about curl local.awslab.internal?
   ```
   curl local.awslab.internal
   ```

   ```
   sh-4.2$ curl local.awslab.internal
   Welcome to my web server. Server private IP is 10.65.2.228
   Availability Zone: us-east-1a
   Stack Name: VPC65
   remote ip is 10.65.2.113
   remote tcp port is 11270
   
   ```

1. and finally, curl global.awslab.internal:
   ```
   curl global.awslab.internal
   ```
   
   ```
   sh-4.2$ curl global.awslab.internal
   Welcome to my web server. Server private IP is 10.65.2.228
   Availability Zone: us-east-1a
   Stack Name: VPC65
   remote ip is 10.64.2.10
   remote tcp port is 45266
   ```

1. You can connect to the VPC65 EC2 instance and try the same commands and compare the results. Which are  different? 

## You have completed the Lab.
