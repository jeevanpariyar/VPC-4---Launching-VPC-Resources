## Introducing Today's Project!

### ✍️ What are we here to do today?

In this project, I will demonstrate how to launch EC2 instances in public and private subnets, configure secure access using security groups and key pairs, and use the Amazon VPC wizard to create and visualize VPC resources efficiently.

I am doing this project to learn how to deploy cloud resources, control network access, and understand how VPC components work together to build a secure AWS network.

### ✍️ What are we doing in this step?

In this step, I will launch two EC2 instances in my existing NextWork VPC: one in the public subnet and another in the private subnet.

I will configure their key pairs and security groups to understand how public and private resources communicate securely within an AWS network

### ✍️ What are we doing in this step?

In this step, I will launch two EC2 instances in my existing NextWork VPC: one in the public subnet and another in the private subnet. I will configure their key pairs and security groups to understand how public and private resources communicate securely within an AWS network

### What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a service that allows me to create an isolated virtual network within AWS. It is useful because it lets me control IP address ranges, create public and private subnets, configure route tables, and manage network access using security groups and network ACLs. This helps me build a secure, organized, and scalable cloud infrastructure.

### How I used Amazon VPC in this project

I used Amazon VPC to create and manage an isolated virtual network for my AWS resources. I launched a public EC2 instance and a private EC2 instance in their respective subnets, configured security groups to control access, and explored the VPC resource map to understand how subnets, route tables, and the internet gateway work together to provide secure network connectivity.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how easily the Amazon VPC wizard could create multiple networking resources together and display their connections in a resource map. I learned how public and private subnets use route tables differently and how security groups help protect private EC2 instances from unauthorized access.

### This project took me...

One thing I didn't expect in this project was how easily the Amazon VPC wizard could create multiple networking resources together and display their connections in a resource map. I learned how public and private subnets use route tables differently and how security groups help protect private EC2 instances from unauthorized access.

## Setting Up Direct VM Access

Directly accessing a virtual machine means logging into and managing the operating system or software of the machine as if you were using it in front of you, but over the internet.

### SSH is a key method for directly accessing a VM

SSH is also as a type of network traffic. Once SSH has established a secure connection between you and the EC2 instance, all data transmitted (including your commands and the responses from the instance) is encrypted. This encryption makes SSH an ideal method for securely exchanging confidential data e.g. login credentials!

### To enable direct access, I set up key pairs

Key pairs help engineers directly access their virtual machines, like EC2 instances.

Just like how documents can be saved in various file formats like PDF, DOCX, or TXT, each suited for different applications or systems, private keys also come in different file formats. Not every system or application can process all these formats, so choosing the right one is crucial.

The .pem format, which stands for Privacy Enhanced Mail, started off as a way to secure emails but has since become the go-to format for managing cryptographic keys because it is supported by many different types of servers e.g. EC2 instances!

## Launching a public server

I had to change my EC2 instance's networking settings by selecting the existing NextWork VPC, choosing the public subnet, and attaching the NextWork Public Security Group. This ensured that my EC2 instance was launched in the correct network with the appropriate security rules and internet connectivity.

### ✍️ What are we doing in this step?

In this steps we will launch private server in private subnet.

In this step, get ready to:\
Launch another EC2 instance (practice makes perfect!)\
Protect your EC2 instance (love this step!)\
Set up a way for your EC2 instances to speak to each other (huuuuge!)

![Launching a public server](https://nextwork.ai/intense_gray_jolly_kokako/uploads/8f49d756-9e51-58c0-856a-e71e54f064ab_88727bef)

## Launching a private server

My private server uses a different security group to improve security and control access.

The NextWork Private Security Group allows SSH traffic only from the NextWork Public Security Group, instead of allowing access from any IP address.

This follows the principle of least privilege and helps protect my private server from unauthorized access.

The source is NextWork Public Security Group. It allows SSH traffic to the private server only from resources associated with that security group, rather than from any IP address.

### ✍️ What are we doing in this step?

In this step, I will use the Amazon VPC wizard to create a new VPC along with its public and private subnets, route tables, and internet gateway. I will also explore the VPC resource map to understand how these networking components are connected.

![Launching a private server](https://nextwork.ai/intense_gray_jolly_kokako/uploads/8f49d756-9e51-58c0-856a-e71e54f064ab_4a9e8014)

## Speeding up VPC creation

I used the Amazon VPC wizard and selected VPC and more to create my new VPC quickly. I set the name prefix to \`nextwork\`, configured the IPv4 CIDR block as \`10.0.0.0/16\`, and created one public subnet (\`10.0.0.0/24\`) and one private subnet (\`10.0.1.0/24\`). I kept NAT gateways and VPC endpoints set to None to avoid additional costs, left DNS options enabled, and used the VPC resource map to visualize how the subnets, route tables, and internet gateway were connected.

A VPC resource map is a visual diagram in AWS that shows how the components of a VPC are connected, including subnets, route tables, and internet gateways. It helps me understand the network architecture at a glance and makes it easier to manage, design, and troubleshoot network connectivity.

My new VPC can have the same IPv4 CIDR block as NextWork VPC because VPCs are isolated from each other by default in AWS. They can use overlapping IP address ranges without conflicts as long as they remain separate. However, overlapping CIDR blocks can cause routing conflicts if I connect the VPCs using VPC peering.

![Speeding up VPC creation](https://nextwork.ai/intense_gray_jolly_kokako/uploads/8f49d756-9e51-58c0-856a-e71e54f064ab_1cbb1b88)

## Speeding up VPC creation

### Tips for using the VPC resource map

I could create 2 public subnets when selecting 2 Availability Zones in the Amazon VPC wizard, with one public subnet in each Availability Zone.

A NAT Gateway allows instances in a private subnet to access the internet for updates and patches while preventing unsolicited inbound connections from the internet. It allows private instances to communicate externally without needing their own public IP addresses.

![Speeding up VPC creation](https://nextwork.ai/intense_gray_jolly_kokako/uploads/8f49d756-9e51-58c0-856a-e71e54f064ab_8ee57662)
