+++
title = "Test Connectivity"
chapter = false
weight = 79
+++

## Test connectivity across Transit Gateway

Now if we have complete all the steps we should be able to test connectivity across the TGW. We will be testing from the first EC2 instance that you created in VPC 10.64.0.0/16. It has an address of **10.64.2.10**. We will be pinging across the Transit Gateway to **10.65.2.10**

   ![Test Diagram](/images/pl-diagram.png)

### Step-by-step

1. From the **Amazon EC2** console and from the left menu select **Instances**.

   ![connect button](/images/test-vpce-list.png)

1. Check the box next to your instance in VPC64 and Click the **Connect** button aboe the list.

   ![connect session manager](/images/testec2-connect.png)

1. Click the radio button next to **Session Manager** and click the **Connect** button. _this will bring up a new browser tab with the Linux bash shell_

   ![ping test](/images/tgw-test-ping.png)

1. At the **sh-4.2\$** prompt,curl the VPC Endpoint DNS name you recorded earlier. _it will look like **vpce-0cb2550d26a0f4c51-9c6sgub0.vpce-svc-0a37df83d8cf5776c.us-east-1.vpce.amazonaws.com**_

   ```
   curl vpce-0cb2550d26a0f4c51-9c6sgub0.vpce-svc-0a37df83d8cf5776c.us-east-1.vpce.amazonaws.com
   ```

   This will return something like the following

   ```
   h-4.2$ curl vpce-0cb2550d26a0f4c51-9c6sgub0.vpce-svc-0a37df83d8cf5776c.us-east-1.vpce.amazonaws.com
   Welcome to my web server. Server private IP is 10.65.2.178
   Availability Zone: us-east-1a
   MY Web Server Demo
   remote ip is 10.65.2.15
   remote tcp port is 46254
   ```

   **_Note: the remote IP is not the IP of the host you are currently on! Instead it is being NAT'ed to the address of the Network Load Balancer in the other VPC. You can contrast this by using curl to the Network Load Balancer over the Transit Gateway (see steps in the Deploy NLB section)_**

1. To verify the IP addresses of the Network Load Balancers you can **dig** the DNS name of the Network Load Balancer** like this:

```
sh-4.2$ dig VPC65-NLB-Internal-b5d244bcb071a9be.elb.us-east-1.amazonaws.com

; <<>> DiG 9.11.4-P2-RedHat-9.11.4-9.P2.amzn2.0.2 <<>> VPC65-NLB-Internal-b5d244bcb071a9be.elb.us-east-1.amazonaws.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 25511
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
;; QUESTION SECTION:
;VPC65-NLB-Internal-b5d244bcb071a9be.elb.us-east-1.amazonaws.com. IN A

;; ANSWER SECTION:
VPC65-NLB-Internal-b5d244bcb071a9be.elb.us-east-1.amazonaws.com. 60 IN A 10.65.2.5
VPC65-NLB-Internal-b5d244bcb071a9be.elb.us-east-1.amazonaws.com. 60 IN A 10.65.3.210

;; Query time: 3 msec
;; SERVER: 10.64.0.2#53(10.64.0.2)
;; WHEN: Tue May 12 23:07:44 UTC 2020
;; MSG SIZE  rcvd: 124
```



### Troubleshooting

If you are unable to ping across, go back and check the route tables. The most common issue is that the private route tables in the VPCs do not have the route to **10.0.0.0/8** pointing to the TGW. 


## You have completed the Lab.
