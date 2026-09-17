**AWS VPC & VPC Peering — Step-by-Step Hands-on Lab
**
This repository documents my hands-on AWS networking lab, where I created VPC infrastructure, configured networking components, established VPC Peering, and tested connectivity between EC2 instances.

☁️ Architecture

The lab includes two VPCs:

Demo VPC: 10.0.0.0/16
Temp VPC: 192.168.0.0/16

The architecture includes:

VPCs
Public & Private Subnets
EC2 Instances
Internet Gateways
Route Tables
VPC Peering
Security Groups
NAT Gateway
🛠️ Implementation Steps
1. Create Demo VPC

Created the primary VPC with CIDR:

10.0.0.0/16
2. Create Subnets

Created:

Public Subnet  → 10.0.0.0/24
Private Subnet → 10.0.1.0/24
3. Configure Internet Gateway

Created and attached an Internet Gateway (IGW) to the Demo VPC.

4. Configure Route Table

Configured the public route table with:

10.0.0.0/16 → local
0.0.0.0/0   → Internet Gateway
5. Launch EC2 Instance

Launched an EC2 instance inside the public subnet and configured its Security Group for required connectivity.

6. Create Second VPC

Created the Temp VPC with:

192.168.0.0/16
7. Create Temp VPC Subnet

Created a public subnet:

192.168.0.0/24
8. Configure Temp VPC Networking

Created the Internet Gateway, Route Table and EC2 instance for the Temp VPC.

9. Create VPC Peering

Created a VPC Peering Connection between:

Demo VPC
10.0.0.0/16
        ↕
Temp VPC
192.168.0.0/16
10. Configure Routes for Peering

Added the required VPC Peering routes so that traffic could be exchanged between the two VPCs.

11. Configure Security Groups

Configured Security Group rules to allow the required traffic between the VPC CIDR ranges.

12. Test Connectivity

Tested connectivity between the EC2 instances using ping.

The connectivity test was successful, confirming communication through the VPC Peering connection.

13. Explore NAT Gateway

Also explored the role of a NAT Gateway for providing outbound internet connectivity to resources in a private subnet.

