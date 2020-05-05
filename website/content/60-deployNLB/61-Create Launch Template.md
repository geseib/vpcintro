+++
title = "Create Launch Template"
chapter = false
weight = 61
+++

## Create Launch Template

It will take a few minutes for the Cloudformation template to to finish launching all of the resources.

1. From the **Amazon EC2** console and from the left menu select **Instances**.

   ![connect button](/images/testec2-list.png)

1. Check the box next to the new instance in the list and Click the **Connect** button aboe the list.

   ![connect session manager](/images/testec2-connect.png)

1. Click the radio button next to **Session Manager** and click the **Connect** button. _this will bring up a new browser tab with the Linux bash shell_

   ![ping test](/images/testec2-ping.png)

1. For the User data enter the following
   ```
   #!/bin/bash
   /usr/bin/yum -y install httpd php
   /sbin/chkconfig httpd on
   /sbin/service httpd start
   /bin/echo -n "Welcome to my web server. Server private IP is " > /var/www/html/index.php
   /opt/aws/bin/ec2-metadata -o | /bin/cut -d" " -f2 >> /var/www/html/index.php
   /bin/echo -n "Availability Zone: " >> /var/www/html/index.php
   /opt/aws/bin/ec2-metadata -z | /bin/cut -d" " -f2 >> /var/www/html/index.php
   /bin/echo "My NLB Demo" >> /var/www/html/index.php
   /bin/echo "remote ip is <?php \$ip = isset(\$_SERVER['HTTP_CLIENT_IP']) ? \$_SERVER['HTTP_CLIENT_IP'] : isset(\$_SERVER['HTTP_X_FORWARDED_FOR']) ? \$_SERVER['HTTP_X_FORWARDED_FOR'] : \$_SERVER['REMOTE_ADDR']; echo \$ip;?>" >> /var/www/html/index.php
   /bin/echo "" >> /var/www/html/index.php
   /bin/echo "remote tcp port is <?php \$port = \$_SERVER['REMOTE_PORT']; echo \$port;?>" >> /var/www/html/index.php
   /bin/echo "" >> /var/www/html/index.php
   /bin/echo "LoadModule remoteip_module modules/mod_remoteip.so" > /etc/httpd/conf.d/remoteip.conf
   /bin/echo "RemoteIPHeader X-Forwarded-For" >> /etc/httpd/conf.d/remoteip.conf
   /bin/echo "RemoteIPInternalProxy 100.64.0.0/10" >> /etc/httpd/conf.d/remoteip.conf
   /bin/echo "RemoteIPProxyProtocol Off" >> /etc/httpd/conf/httpd.conf
   /bin/echo "RemoteIPProxyProtocolExceptions 127.0.0.1 100.64.0.0/10" >> /etc/httpd/conf/httpd.conf

/sbin/service httpd restart
`This will return something like the following`
PING www.example.com (93.184.216.34) 56(84) bytes of data.
64 bytes from 93.184.216.34 (93.184.216.34): icmp_seq=1 ttl=52 time=1.55 ms
64 bytes from 93.184.216.34 (93.184.216.34): icmp_seq=2 ttl=52 time=0.939 ms
64 bytes from 93.184.216.34 (93.184.216.34): icmp_seq=3 ttl=52 time=0.814 ms
^C
--- www.example.com ping statistics ---
3 packets transmitted, 3 received, 0% packet loss, time 2003ms
rtt min/avg/max/mdev = 0.814/1.102/1.555/0.326 ms
`1. We can determine what public IP address you are using to get to the internet resource by the following command:`
dig +short myip.opendns.com @resolver1.opendns.com
`That will return something like:`
h-4.2\$ dig +short myip.opendns.com @resolver1.opendns.com
54.85.184.24
```

    You can also try the following:
    ```
    curl www.example.com
    ping www.amazon.com
    ```

### Troubleshooting

If you have any issues, it likely shows up with the fact that you cannot connect to the Ec2 Instance. See if you can troubleshoot it yourself, walking through the steps.

The following are good places to start:
There are several steps that could be causing the issue.

1. Is the ec2 Instance in a **Private** subnet?
1. Is the IAM role you created attached to the EC2 instance
1. Does the IAM role have the **AmazonSSMManagedInstanceCore**
1. Are the correct route tables attached the subnets (Public route table to both public subnets and the PRivate route table to the Private subnets)
1. Did you add the 0.0.0.0/0 route to the IGW on the public route table and the 0.0.0.0/0 route to the NGW on the private route table.

## You have completed the Lab.
