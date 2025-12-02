# Lab Summary: Introduction to Amazon Linux AMI, SSH Access & Linux Man Pages

This lab demonstrated how to securely connect to an Amazon Linux AMI via SSH and explore the Linux manual page system (`man`). It introduced basic Linux command-line usage within an EC2 instance and showed how built-in documentation helps users learn commands, syntax, and options.

---

## Connecting to an Amazon Linux AMI Using SSH

- Accessed AWS via Vocareum Lab Console
- Retrieved:
  - Public IP address of the EC2 instance
  - SSH key file (`.pem` for macOS/Linux or `.ppk` for Windows)
- Used SSH to connect to the Amazon Linux instance:
  - Windows users used **PuTTY**
  - macOS/Linux users used the terminal command:

    ```
    ssh -i labsuser.pem ec2-user@<public-ip>
    ```

- Adjusted key permissions (`chmod 400`) to enforce secure authentication
- Logged in as the default Linux user: **ec2-user**

**Goal:** Understand how key-based SSH authentication securely connects you to Linux servers running in AWS.

---

## Navigating Linux Manual (“man”) Pages

- Used `man man` to access documentation for the `man` tool itself
- Learned to navigate man pages with arrow keys
- Located important informational headers, including:
  - **NAME**
  - **SYNOPSIS**
  - **DESCRIPTION**
  - **FILES**
  - **OPTIONS**
  - **SEE ALSO**
- Identified how man pages describe:
  - purpose of the command
  - command usage
  - valid flags and parameters
- Exited man pages using `q`

**Goal:** Demonstrate how Linux’s built-in manuals provide detailed command-level help and reference material.

---

# Key Lessons Learned

- SSH uses cryptographic key pairs instead of passwords for secure login  
- Linux man pages are essential for learning commands directly in the terminal  
- Headers in man pages explain what a command does and how to use it  
- Keys must be read-only (`chmod 400`) to prevent insecure SSH usage  
- Real AWS EC2 hosts can act as Linux terminals for education, development, or deployment  

---

# Final Summary

This lab provided practical experience with:
- Remote Linux access using SSH  
- Secure key-based authentication  
- Navigating Linux terminal environments  
- Using man pages for command discovery and guidance  

These foundational Linux and SSH skills are crucial for cloud administration, DevOps, security, and general Linux proficiency.

---

# Architecture Diagram

                  ┌──────────────────────────┐
                  │   User Local Computer     │
                  │  (PuTTY/SSH Terminal)     │
                  └───────────▲───────────────┘
                              │ SSH Connection
                              │ Using Key Pair
                              │
                  ┌───────────┴─────────────┐
                  │     EC2 Instance         │
                  │  Amazon Linux AMI Host   │
                  │  Username: ec2-user      │
                  │  Shell Access Enabled    │
                  └───────────▲─────────────┘
                              │
                              │ Inside Lab AWS Network
                              │
                 ┌────────────┴─────────────┐
                 │         Public Subnet     │
                 │  (Reachable via Internet) │
                 └────────────▲─────────────┘
                              │
                              │
                 ┌────────────┴─────────────┐
                 │         Lab VPC           │
                 │ Virtual Private Network   │
                 │ Hosting EC2 Instance      │
                 └───────────────────────────┘
