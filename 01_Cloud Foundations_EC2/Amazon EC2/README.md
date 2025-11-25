# Introduction to Amazon EC2

## Overview
This lab introduces the core concepts of Amazon EC2, including launching, configuring, monitoring, resizing, and terminating an instance. You will deploy a simple web server, modify its security settings, scale the instance, and test termination protection.

---

## Topics Covered
- Launch an EC2 instance with termination protection  
- Deploy a web server using User Data  
- Monitor instance status and CloudWatch metrics  
- Modify a security group to allow HTTP access  
- Resize the instance type and EBS volume  
- Test termination protection  
- Terminate the instance safely  

---

## Task 1: Launching Your EC2 Instance
You launch an EC2 instance named **Web Server** using the Amazon Linux 2023 AMI and the **t3.micro** instance type.  
You create a security group without SSH access and use User Data to automatically install and start an Apache web server.

---

## Task 2: Monitoring Your Instance
You view EC2 status checks (system + instance reachability) and explore CloudWatch metrics such as CPU and network activity.  
You also capture an instance screenshot for troubleshooting visibility.

---

## Task 3: Updating the Security Group
When accessing the instance’s public IP, the page initially fails because HTTP traffic isn’t allowed.
You update the security group to add an inbound rule for **HTTP (port 80)**, enabling you to see the webpage:  
“Hello From Your Web Server!”

---

## Task 4: Resizing the Instance
Stop the instance to make changes, then:
- Change the instance type from **t3.micro → t3.small**  
- Increase the EBS root volume from **8 GiB → 10 GiB**  
After restarting, the instance has more memory and storage.

---

## Task 5: Testing Termination Protection
Termination initially fails because termination protection is enabled.  
After disabling it, the instance is successfully terminated.

---

## Lab Complete
i launched, configured, monitored, resized, protected, and terminated an EC2 instance while learning key EC2 management concepts.

---
