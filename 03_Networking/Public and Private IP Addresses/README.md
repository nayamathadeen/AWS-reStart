# Internet Protocols – Public and Private IP Addresses (Lab Summary)

## Overview
This lab focuses on troubleshooting network connectivity issues within an AWS environment. You take on the role of a Cloud Support Engineer assisting a customer whose EC2 instance cannot reach the internet. Throughout the lab, you investigate the difference between public and private IP addressing, connect to EC2 instances using SSH, and provide recommendations regarding VPC CIDR choices.

---

## Objectives
- Understand the customer scenario and reproduce the issue  
- Compare private vs public IP addressing in AWS  
- Troubleshoot EC2 connectivity using layered approaches  
- Explain why using a public IP range for a VPC is not recommended  
- Summarize findings for the customer  

---

## Scenario Summary
A customer (Jess) has a VPC (10.0.0.0/16) with two EC2 instances in the same subnet:

- Instance A: Cannot reach the internet  
- Instance B: Can reach the internet  

The customer suspects the issue is related to instance configuration and also asks whether using a public IP range such as 12.0.0.0/16 for a new VPC is acceptable.

I was tasked with investigating.

---

## Task 1: Investigating the Environment
After comparing both instances in the AWS EC2 console:

- Instance B has a public IPv4 address, allowing internet connectivity.  
- Instance A only has a private IPv4 address, meaning it cannot reach the internet, even if routing and subnets are correct.

### Key Insight
Private IPs are used within the VPC. They cannot be accessed from the public internet without NAT or a public IP address.

---

## Task 2: SSH Connectivity
I attempted to SSH into both instances using:

- PuTTY (.ppk key) – Windows   

### Outcome
- I could connect to Instance B  
- I could NOT connect to Instance A  

### Reason
Instance A has no public IP, so it is unreachable from outside the VPC. SSH requires a routable public IP or a bastion/NAT setup.

---

## Why Not Use a Public IP Range for a VPC?
Jess asked about using a public IP range like 12.0.0.0/16 as a VPC CIDR.

### Recommendation: Do NOT use publicly routable IP ranges for VPCs.

### Reasons
- Public IP ranges are globally assigned and routable on the internet  
- AWS VPCs are designed to use private address spaces (RFC1918)  
- Using a public range can cause:  
  - Routing conflicts  
  - Unpredictable network behavior  
  - Potential overlaps with real internet IPs  
  - Security risks  

### Valid private ranges (RFC1918)
- 10.0.0.0/8  
- 172.16.0.0/12  
- 192.168.0.0/16  

---

## Key Takeaways
- EC2 instances need a public IP or NAT access to reach the internet.  
- Private IPs are internal to the VPC.  
- Public IPs allow communication with the outside world.  
- VPC CIDR blocks must use private IP ranges for reliability and compliance with RFC1918.  
- Troubleshooting cloud networking often mirrors OSI-style layered analysis.  

---

## References
- AWS EC2 IP Addressing  
- AWS VPC CIDR Documentation  
- RFC1918 – Private Network Addressing  
