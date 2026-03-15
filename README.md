# How-to-setup-an-AWS-Site-to-Site-S2S-VPN-Connection
Hands-on AWS networking and cloud security lab demonstrating how to build a secure Site-to-Site VPN connection between an on-premises network and an Amazon VPC using IPsec.
# How to Setup an AWS Site-to-Site (S2S) VPN Connection

## Overview

Hybrid cloud architectures are common in modern enterprises. Many organizations operate infrastructure both on-premises and in the cloud, requiring secure connectivity between the two environments.

This lab demonstrates how to establish a **Site-to-Site (S2S) VPN connection between an on-premises network and an Amazon VPC** using IPsec.

Since an actual on-premises network was not available, the lab simulates a corporate network using a VPC and EC2 instance acting as a router.

The objective was to create a secure encrypted tunnel that allows communication between resources in two different network environments.

---

# What is Amazon VPC?

Amazon Virtual Private Cloud (VPC) allows organizations to create a **logically isolated network inside AWS** where resources such as EC2 instances, databases, and load balancers can run securely.

A VPC allows you to control:

• IP address ranges (CIDR blocks)  
• Subnet segmentation  
• Route tables controlling traffic flow  
• Internet connectivity  
• Network security controls

This makes it possible to design enterprise-grade network architectures in the cloud.

---

# What is Amazon EC2?

Amazon Elastic Compute Cloud (EC2) provides **scalable virtual servers in AWS**.

EC2 instances can host applications, databases, networking tools, and infrastructure services.

In this lab, EC2 instances were used to simulate:

• A router representing the on-premises network  
• A private workload within the AWS VPC

---

# What is AWS Site-to-Site VPN?

AWS Site-to-Site VPN enables secure communication between **an on-premises network and an Amazon VPC**.

It uses **IPsec encrypted tunnels** over the public internet to securely transmit data.

Key components include:

Customer Gateway – represents the on-premises router  
Virtual Private Gateway – the VPN concentrator on the AWS side  
VPN Tunnel – encrypted connection between networks  
Site-to-Site VPN Connection – configuration linking both environments

---

# Why This Lab Matters

Many enterprises operate **hybrid cloud environments**, where applications run partly in the cloud and partly in on-premises data centers.

Without secure connectivity, organizations cannot safely extend internal services to the cloud.

Site-to-Site VPN enables:

• Secure hybrid networking  
• Encrypted communication across environments  
• Controlled network expansion into AWS  
• Secure remote infrastructure integration

---

# Problem Solved

The challenge addressed in this lab:

How can we securely connect an on-premises network to an AWS VPC?

By default, instances inside a VPC cannot communicate with external corporate networks.

This lab demonstrates how to establish a secure encrypted tunnel between networks to enable safe communication.

---

# Why This Solution Makes Sense

Site-to-Site VPN allows organizations to extend their internal networks into AWS without exposing traffic to the public internet.

Advantages include:

• Encrypted IPsec tunnels  
• Secure hybrid architecture  
• Controlled connectivity between networks  
• Seamless communication between workloads

This architecture is commonly used when migrating applications to the cloud while maintaining existing infrastructure.

---

# Lab Architecture

The lab simulates two network environments:

Mumbai Region (ap-south-1)
Simulated On-Premises Corporate Network

• VPC  
• Public subnet  
• EC2 instance running Openswan acting as router

N. Virginia Region (us-east-1)
AWS Cloud Environment

• VPC  
• Private subnet  
• EC2 instance representing cloud workload  
• Virtual Private Gateway

Both networks were connected using a **Site-to-Site VPN connection**.

---

# Lab Steps

1. Create a VPC in Mumbai Region
2. Create a Public Subnet
3. Attach an Internet Gateway
4. Create and configure Route Tables
5. Launch EC2 instance acting as on-premises router
6. Create VPC in N. Virginia Region
7. Create Private Subnet
8. Launch EC2 instance inside AWS VPC
9. Create Customer Gateway
10. Create Virtual Private Gateway
11. Create Site-to-Site VPN connection
12. Configure Openswan router
13. Test connectivity between networks

---

# How It Works

1. Traffic originates from the simulated on-premises network.
2. The EC2 router sends traffic through the IPsec VPN tunnel.
3. The encrypted tunnel connects to the Virtual Private Gateway in AWS.
4. AWS decrypts the traffic and routes it inside the VPC.
5. The private EC2 instance receives the traffic securely.

This creates a **secure hybrid network architecture between on-premises and cloud infrastructure**.

---

# Security Insight

One of the key challenges in hybrid environments is protecting traffic that travels between networks.

Site-to-Site VPN ensures that:

• Data is encrypted using IPsec  
• Communication between environments remains private  
• Internal systems can safely extend to cloud infrastructure

This architecture helps organizations adopt the cloud without sacrificing network security.

---

# Skills Demonstrated

AWS networking architecture  
Amazon VPC design  
EC2 deployment  
Site-to-Site VPN configuration  
Customer Gateway configuration  
Virtual Private Gateway setup  
Hybrid cloud networking  
Secure tunnel configuration

---

# Security insights

Hybrid cloud architectures require secure connectivity between environments.

AWS Site-to-Site VPN enables organizations to extend their internal networks into the cloud while maintaining encrypted and controlled communication.

Understanding how these architectures work is essential for cloud engineers and security teams managing hybrid infrastructure.

