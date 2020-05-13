+++
title = "Create Launch Template"
chapter = false
weight = 61
+++

## Create Launch Template

[Launch templates](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-launch-templates.html) enable you to store launch parameters so that you do not have to specify them every time you launch an instance. For example, a launch template can contain the AMI ID, instance type, and network settings that you typically use to launch instances. We will use a Launch template for our Auto Scaling group to launch EC@ instances without requiring intervention during launch.

   ![Launch templates](/images/nlb-lts.png)
1. From the **Amazon EC2** console and from the left menu select **Launch Templates**. Click the **Create launch template** button.

   ![Launch template](/images/nlb-lt.png)

1. Create a launch template with the following:
   - **Launch template name**: name it, like **basicwebserver**
   - **Template version description**: give it a description.
   - check the box next to **Provide guidance to help me set up a template that I can use with EC2 Auto Scaling**

   ![ami and instance type](/images/nlb-lt-ami.png)

1. Scroll down and enter the following:
   - **AMI**: Select the first AMI in the list **Amazon Linux 2 AMI (HVM)**
   - **Security Group**: Select the security group created in the prvious step from the list.
   - **Instance tags**: Click **add tag** button and use **key**: **Name**  and give it a Value: **VPC65-NLB-Webserver**


   ![ami and instance type](/images/nlb-lt-net.png)

1. Scroll down and enter the following network configuration:
   - **Networking platform**: Leave checked **Virtual Private Cloud(VPC)**
   - **Instance type**: Tpye or Select **t2.micro** from the list.
   - Leave **Key pair** at default **Don't include in launch template**
   - Click the **Create launch template** button.

   ![success](/images/nlb-lt-success.png)
1. Once the **Launch template** is created, click the **View launch template** to get back to the **EC2** console.

### Create new Version of Launch template
It seems we forgot something on our launch template. We want our EC2 instance to be fully functional web servers at launch. The good news, is Launch templates support versions, so lets modify our Launch template with a new version.

   ![Launch templates](/images/nlb-lt-modify.png)
1. From the **Amazon EC2** console and from the left menu select **Launch Templates**. With your Launch template selected from the list, click the **Action** button. Select **Modify template (Create new version)**

1. Enter a **Template version description** such as **add user data with http server**

   ![Launch templates](/images/nlb-lt-userdata.png)
1. Scroll down and expand the **Advanced details** section. Scroll down again to the bottom. Click the copy button below and Enter the following in the **User data** box.

```
#!/bin/bash
/usr/bin/yum -y install httpd php
/sbin/chkconfig httpd on
/sbin/service httpd start
/bin/echo -n "Welcome to my web server. Server private IP is " > /var/www/html/index.php
/opt/aws/bin/ec2-metadata -o | /bin/cut -d" " -f2 >> /var/www/html/index.php
/bin/echo -n "Availability Zone: " >> /var/www/html/index.php
/opt/aws/bin/ec2-metadata -z | /bin/cut -d" " -f2 >> /var/www/html/index.php
/bin/echo "NLB Web Server Lab" >> /var/www/html/index.php
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
```
1. Click the **Create template version**.

   ![success](/images/nlb-lt-mod-success.png)
1. Once the **Launch template** is created, click the **View launch template** to get back to the **EC2** console.

## You have completed the Launch template.
