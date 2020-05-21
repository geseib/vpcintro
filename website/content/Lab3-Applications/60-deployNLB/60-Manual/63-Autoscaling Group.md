+++
title = "Create Autoscaling Group"
chapter = false
weight = 63
+++

### Autoscaling Group

Amazon [EC2 Auto Scaling](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-launch-templates.html)helps you ensure that you have the correct number of Amazon EC2 instances available to handle the load for your application. You create collections of EC2 instances, called Auto Scaling groups.

  ![Auto scaling group](/images/nlb-asgs.png)
1. From the **Amazon EC2** console and from the left menu, near the bottom, select **Auto Scaling Groups**. Click the **Create Auto Scaling group** button.

   ![basic config](/images/nlb-asg.png)

1. Select the option for the **Launch Template** on the right and check the box next to your **Launch template** from the list. Click **Next Step**.

   ![create ASG](/images/nlb-asg-config.png)
1. Create an **Auto Scaling Group** with the following:
   - Leave the **Choose target type** as **Instances**.
   - **Group name**: name it, like **basicwebservers**.
   - **Launch Template Version**: make sure it is on **2** _this is where we added the user data_.
   - **Group size**: change to Start with **2** instances.
   - **Network**: select the VPC65 **10.65.0.0/16** from the dropdown list.
   - **Subnet**: Select both of the private subnets **VPC65-PrivateA** and **VPC65-PrivateB**
   

   ![health check](/images/nlb-asg-advanced.png)

1. Scroll down and expand the **Advanced details** section and check the box next to **Receive traffic from one or more load balancers**. Then enter the following:
   - **Target Groups**: select your target group from the list
   - **Health Check Type**: Change to **ELB** _this tells the Auto scaling group to remove/replace an instance if it is not responsive to the Load balancers health check vs just being a healthy EC2 instance_.
   - Click the **Next: Configure scaling policies**.

   ![create scaling](/images/nlb-asg-scaling.png)

1. Create an **Auto Scaling Group** scaling policy:
   - Check **Use scaling policies to adjust the capacity of this group**.
   - Change **Scale between 2 and 4 instances. These will be the minimum and maximum size of your group.**.
   - Leave the **Name**: **Scale Group Size**.
   -  Leave the **Metric Type**: **Average CPU Utilization**.
   - Set **Taget Value** to something like **70**
   - Click the **Review** button.

   ![Review](/images/nlb-asg-review.png)

1. Review that you have everything entered correctly and click the **Create Auto Scaling group** button.

## You have created the Auto Scaling group.