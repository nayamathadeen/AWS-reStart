# Lab Summary: Internet Protocols – Static and Dynamic Addresses

This lab demonstrated the difference between dynamically assigned and statically assigned IP addresses in AWS. The lab focused on troubleshooting a real-world customer issue where an EC2 instance’s public IP address changed every time the instance was stopped and started, causing dependent resources to fail.

By investigating EC2 networking behavior and applying AWS best practices, a permanent solution was implemented using an Elastic IP (EIP), ensuring consistent public connectivity for the instance.

---

## Investigating the Customer Scenario

- Reviewed a customer support ticket reporting changing public IP addresses
- Identified that the EC2 instance relied on a dynamically assigned public IP
- Replicated the issue by launching and restarting an EC2 instance
- Observed that the public IP address changed after each stop/start cycle

**Goal:** Understand why public IP addresses change on EC2 instances.

---

## Understanding Static vs Dynamic IP Addresses

- Dynamic public IPs are automatically assigned by AWS
- Dynamic public IPs are released when an instance is stopped
- Private IP addresses remain consistent within the VPC
- Static IPs are required when external systems depend on a fixed address

**Goal:** Identify when a static IP address is required.

---

## Implementing a Solution Using Elastic IPs

- Allocated an Elastic IP (EIP)
- Associated the EIP with the EC2 instance
- Verified that the public IP address no longer changed
- Restarted the instance to confirm persistence

**Goal:** Assign a permanent public IP address to an EC2 instance.

---

## Key Lessons Learned
- Public IPs assigned automatically are dynamic by default
- Stopping an EC2 instance releases its public IP
- Elastic IPs provide static, persistent public IP addresses
- Static IPs are required for stable external connectivity
- AWS provides managed solutions for common networking challenges

---

## Final Summary
This lab provided hands-on experience with:

- Diagnosing dynamic IP address behavior
- Understanding EC2 public and private IP assignment
- Using Elastic IPs to solve real-world networking problems
- Applying AWS networking best practices in a support scenario

These skills are essential for cloud networking, infrastructure troubleshooting, and customer-facing cloud support roles.

---

## Architecture Diagram

```text
              ┌──────────────────────────┐
              │        Internet          │
              └───────────▲──────────────┘
                          │
                    Elastic IP
                          │
              ┌───────────┴─────────────┐
              │     EC2 Instance         │
              │     Public Subnet        │
              │   Elastic IP Attached   │
              └───────────▲─────────────┘
                          │
              ┌───────────┴─────────────┐
              │           VPC            │
              │       Private CIDR       │
              └─────────────────────────┘
