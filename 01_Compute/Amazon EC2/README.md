# Lab Summary: Introduction to Amazon EC2

This lab demonstrated how to deploy, secure, monitor, scale, and remove a cloud-based virtual server using Amazon EC2. It showed how EC2 provides flexible, pay-as-you-go computing resources that can be created within minutes and adjusted as requirements change.

---

## Launching an EC2 Instance

- Opened the AWS Management Console and created an EC2 instance named **Web Server**
- Used the default **Amazon Linux 2023** image
- Selected **t3.micro** as the instance type
- Skipped key-pair login (not required for this lab)
- Chose **Lab VPC** as the network
- Created a new Security Group with no inbound access
- Enabled **Termination Protection** to prevent accidental deletion
- Added a **User Data script** that:
  - Installs Apache (httpd)
  - Starts the web service on boot
  - Creates a simple HTML page:
    ```
    Hello From Your Web Server!
    ```

**Goal:** Understand how to deploy an EC2 instance, automate setup, and protect it from accidental termination.

---

## Monitoring the Instance

- Checked EC2 health checks for software and hardware status
- Viewed performance metrics under the Monitoring tab (powered by CloudWatch)
- Captured an instance screenshot to simulate console-level visibility

**Goal:** Learn how AWS monitors instance health and provides tools for basic troubleshooting.

---

## Accessing the Web Server (Security Group Update)

At first the web page couldn’t load because the Security Group blocked all inbound traffic.

To fix this:
- Added an inbound rule:
  - **HTTP (Port 80)**
  - Source: Anywhere (IPv4)
- Refreshed the browser using the instance’s Public IP
- Successfully viewed the webpage message

**Goal:** Understand that Security Groups act like virtual firewalls that control what can reach an EC2 instance.

---

## Resizing the EC2 Instance & Storage

To simulate scaling:
1. Stopped the instance
2. Changed instance type from **t3.micro → t3.small** (more RAM)
3. Increased root disk size from **8 GiB → 10 GiB**
4. Started the instance again

**Goal:** See how EC2 resources can be scaled up when workloads grow.

---

## Testing Termination Protection

- Tried to delete the instance — termination failed due to protection
- Disabled termination protection manually
- Then successfully terminated the instance

**Goal:** Learn how AWS prevents accidental deletion and how to control that setting.

---

# Key Lessons Learned

- EC2 instances are virtual servers that can launch in minutes  
- Security Groups control network access  
- User Data scripts allow automated configuration on launch  
- CloudWatch metrics help monitor instance health  
- Compute power and storage can be resized at any time  
- Termination protection prevents accidental loss of instances  

---

# Final Summary

This lab gave practical exposure to:
- deploying an EC2 instance  
- configuring security  
- building a simple web server  
- monitoring performance  
- scaling resources  
- terminating safely

It highlights the flexibility of EC2:
- scale only when needed  
- pay only for capacity used  
- control access and security  
- automate configuration  
- maintain visibility on health and performance  

---

# Architecture Diagram

                           ┌──────────────────────────┐
                           │        Internet          │
                           │   (User Web Browser)     │
                           └───────────▲──────────────┘
                                       │  HTTP (Port 80)
                                       │
                                       │
                             ┌─────────┴───────────┐
                             │   Security Group     │
                             │  "Web Server SG"     │
                             │ Inbound Rule:        │
                             │   HTTP from Anywhere │
                             └─────────▲───────────┘
                                       │ Allowed Traffic
                                       │
                           ┌───────────┴──────────────┐
                           │    EC2 Instance          │
                           │  Amazon Linux 2023       │
                           │  User Data Script:       │
                           │   - Install Apache       │
                           │   - Start Web Server     │
                           │   - Create Web Page      │
                           │ Public IPv4 Address →    │
                           │ View Web Page            │
                           └───────────▲──────────────┘
                                       │
                                       │ Inside VPC
                                       │
                   ┌───────────────────┴──────────────────┐
                   │               Subnet                 │
                   │      (Part of the Lab VPC)           │
                   └───────────────────▲──────────────────┘
                                       │
                                       │
                   ┌───────────────────┴──────────────────┐
                   │                Lab VPC                │
                   │ Virtual Private Cloud Network where   │
                   │ all traffic and access is controlled  │
                   └───────────────────────────────────────┘

