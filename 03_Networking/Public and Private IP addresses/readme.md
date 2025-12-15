# Lab Summary: Internet Protocols – Public and Private IP Addresses

This lab demonstrated how public and private IP addresses function within an AWS Virtual Private Cloud (VPC) and how they impact connectivity to Amazon EC2 instances. The lab focused on troubleshooting a customer networking issue by analyzing IP addressing, understanding CIDR ranges, and applying structured troubleshooting methods.

The scenario simulated a real-world cloud support case where two EC2 instances existed in the same VPC and subnet, yet only one instance was able to reach the internet. By investigating instance networking details and testing connectivity, the root cause of the issue was identified.

---

## Investigating the Customer Environment

- Reviewed a customer support ticket describing inconsistent internet connectivity between two EC2 instances
- Analyzed a VPC with a CIDR range of `10.0.0.0/16`
- Identified two EC2 instances (Instance A and Instance B) with similar configurations
- Compared public and private IPv4 addresses assigned to each instance

**Goal:** Understand how IP addressing affects network reachability in AWS.

---

## Analyzing Public vs Private IP Addresses

- Examined the networking details of both EC2 instances
- Observed that:
  - Instance A had only a private IP address
  - Instance B had both a private IP and a public IP address
- Determined that private IP addresses are only reachable within a VPC
- Confirmed that public IP addresses enable access from outside the VPC

**Goal:** Identify why only one EC2 instance could access the internet.

---

## Connecting to EC2 Using SSH

- Used SSH utilities (PuTTY or terminal) to attempt connections to both instances
- Successfully connected to Instance B using its public IP address
- Failed to connect to Instance A due to lack of a public IP
- Validated that SSH access from the internet requires a public IP address

**Goal:** Demonstrate how IP address type determines external connectivity.

---

## Advising on CIDR Range Selection

- Evaluated the customer’s question about using a public IP range (e.g. `12.0.0.0/16`) for a VPC
- Identified risks including IP conflicts and routing issues
- Confirmed best practice is to use RFC 1918 private IP ranges for VPCs:
  - 10.0.0.0/8
  - 172.16.0.0/12
  - 192.168.0.0/16

**Goal:** Provide guidance on proper IP address planning in AWS.

---

## Key Lessons Learned
- Public IP addresses allow access from outside the VPC
- Private IP addresses are only reachable within the VPC
- EC2 instances can appear identical but behave differently based on IP assignment
- Troubleshooting networking issues requires layered analysis
- AWS VPCs should use private CIDR ranges to avoid conflicts

---

## Final Summary
This lab provided hands-on experience with:

- Identifying differences between public and private IP addresses
- Troubleshooting EC2 connectivity issues
- Applying structured troubleshooting approaches
- Advising customers on AWS networking best practices

These skills are essential for cloud support engineers, network troubleshooting, and designing secure AWS architectures.

---

## Architecture Diagram


              ┌──────────────────────────┐
              │        Internet          │
              └───────────▲──────────────┘
                          │
                 Public IP Access
                          │
              ┌───────────┴─────────────┐
              │     EC2 Instance B       │
              │   Public + Private IP    │
              └───────────▲─────────────┘
                          │
                          │ Private Network
                          │
              ┌───────────┴─────────────┐
              │     EC2 Instance A       │
              │     Private IP Only      │
              └───────────▲─────────────┘
                          │
              ┌───────────┴─────────────┐
              │           VPC            │
              │       10.0.0.0/16        │
              └─────────────────────────┘
