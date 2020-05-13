+++
title = "Create IAM Role"
chapter = false
weight = 40
+++

## Create an IAM Role for the EC2 Instance

IAM Roles can be used as Instance Profiles, giving the EC2 instance permissions. For example, this could be to permit access to Amazon S3 for object storage or to DynamoDB for NoSQL queries. In this case we are using it for remote bash access using AWS Systems Manager.


![IAM Roles](/images/iam-roles.png)
1. From the **Amazon IAM** console and from the left menu select Roles. Click **Create role** button.

    ![Select trusted Entity](/images/iam-selectentity.png)
1. Select type of trusted entity with the following selections:
    - Keep the **AWS service** as the trusted entity.
    - Highlight **EC2** from the use cases.
    - Click the **Next:Permissions** button.

    ![Select policy](/images/iam-selectpolicy.png)
1. Attach Policy Permissions:
    - In the **filter policy** search box, type **ssm**.
    - Check the box next to **AmazonSSMManagedInstanceCore** from the policy names.
    - Click the **Next:Tags** button.

   ![Select tags](/images/iam-tags.png)
1. At the next screen, click the **Next:Review** button. 

   ![Select name](/images/iam-namerole.png)
1. At the next screen, give the role a **Role name** such as **VPC64-EC2-role**. Click the **Create role** button. 



### You have completed the IAM Role for the EC2 Instance. ###

