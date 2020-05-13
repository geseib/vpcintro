+++
menutitle = "Build a VPC"
chapter = false
weight = 30
+++

## Creating your First VPC from Scratch

There are several ways to quickly create a VPC. You can Launch the VPC Wizard in the [Amazon VPC Console](https://aws.amazon.com/getting-started/) or use Infrastrucutre as code using [AWS Cloudformation](https://aws.amazon.com/cloudformation/) **We will do this later in the workshop**. However; in this workshop, we will build a VPC piece by piece, so we can see all of the components.
![Basic VPC Diagram](/images/vpc_intro_complete_diagram.png)

#### What we will do:

1. Create a **Virtual Private Cloud**(**VPC**), defining its IP CIDR block.
1. Create four(4) **subnets**: _2 Public and 2 Private_.
1. Create an **Internet Gateway**.
1. Create a **Virtual Private Gateway**
1. Create a **NAT Gateway**
1. Create a **route table** named **public**; with a default route to the Internet Gateway, and associate to public subnets.
1. Create a **route table** named **private**; with a default route to the NAT Gateway, and associate to private subnets.

