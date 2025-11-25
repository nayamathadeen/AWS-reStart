 Internet Protocols – Static and Dynamic Addresses (Lab Summary)

## Overview
This lab focuses on troubleshooting static and dynamic IP behavior in AWS. Acting as a Cloud Support Engineer, you investigate why an EC2 instance’s public IP changes every time it is stopped and started. You then implement the correct AWS solution to provide a persistent (static) public IP address.

---

## Objectives
- Summarize the customer scenario  
- Compare static vs dynamic IP addressing in AWS  
- Launch and test an EC2 instance to replicate the issue  
- Assign a persistent Elastic IP (EIP)  
- Develop and present a solution  

---

## Scenario Summary
A customer named **Bob** reports that his EC2 instance’s **public IP changes every time the instance is stopped and started**.  
This causes system failures because the instance relies on a fixed IP address.

Customer architecture includes:
- A VPC  
- Internet Gateway  
- Public Subnet  
- One EC2 instance (“Public Instance”)

My job is to determine why the IP changes and provide a permanent solution.

---

## Task 1: Investigating the Environment

### Replicating the Issue
You launched a new EC2 instance with:
- Amazon Linux 2  
- t3.micro  
- Public Subnet  
- Auto-assign Public IP: **Enabled**

After launching I:
1. Checked the public and private IPv4 addresses  
2. Stopped the instance → public IP changed  
3. Started the instance → public IP changed again  

### Findings
- **Public IP Address:** Dynamic — changes every stop/start  
- **Private IP Address:** Static — stays the same  

I successfully replicated Bob’s issue.

---

## Assigning a Static Public IP (Elastic IP)

To fix the issue:
1. Navigate to **Elastic IPs** under “Network & Security”  
2. Allocate a new Elastic IP  
3. Associate the EIP with the EC2 instance  

### Result
- The Elastic IP becomes the instance’s **permanent public IP**  
- Stopping and starting the instance **no longer affects** the public IP  

This fully resolves the customer’s issue.

---

## Task 2: Customer Response Summary

As the Cloud Support Engineer:

1. The instance was receiving a **dynamic public IP**, which changes automatically.  
2. Private IPs remain the same, but public IPs do not unless an EIP is used.  
3. An **Elastic IP (EIP)** provides a **persistent, static public IPv4 address**.  
4. After attaching the EIP, the IP now remains the same across restarts.

---

## Key Takeaways
- Dynamic public IPs change every stop/start  
- Private IPs remain static inside the VPC  
- Elastic IPs offer **persistent, stable public IP addresses**  
- EIPs are the correct AWS solution when a fixed public IP is required  
- Troubleshooting involves replication, analysis, and applying AWS best practices  

---

## Recap
- Recreated the customer’s issue  
- Observed dynamic vs static IP behavior  
- Allocated and attached an Elastic IP  
- Verified the IP remained constant after restarts  
- Provided a complete and accurate solution to the customer  
