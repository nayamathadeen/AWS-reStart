# Lab Summary: Introduction to Amazon Aurora

This lab demonstrated how to create and interact with an Amazon Aurora database using the Amazon RDS service. It introduced Aurora as a fully managed, MySQL-compatible relational database engine and showed how it integrates with Amazon EC2 instances for secure database access and querying.

The lab focused on provisioning an Aurora database, connecting to it from a pre-created EC2 Linux instance, configuring database connectivity, creating tables, inserting data, and running SQL queries.

---

## Working with Amazon Aurora

### Creating an Aurora Database Instance
- Created an Aurora (MySQL-compatible) database using Amazon RDS
- Selected a Dev/Test template suitable for non-production workloads
- Configured database credentials and instance class
- Deployed the database into a private subnet within a Lab VPC
- Disabled public access to ensure secure, private connectivity

**Goal:** Understand how to provision and configure a managed relational database using Amazon Aurora.

---

## Connecting to an Amazon EC2 Instance

- Accessed a pre-created Amazon EC2 Linux instance named **Command Host**
- Connected using AWS Session Manager (browser-based terminal)
- Avoided the need for SSH keys or public IP exposure

**Goal:** Learn how EC2 instances can be used as secure clients for database access.

---

## Configuring EC2 to Connect to Aurora

- Installed the MariaDB client using the `yum` package manager
- Retrieved the Aurora cluster writer endpoint from the RDS console
- Connected to the Aurora database using MySQL client credentials
- Verified successful database connection through the MariaDB monitor

**Goal:** Configure a Linux-based EC2 instance to communicate with an Aurora database.

---

## Creating and Querying Database Tables

- Listed available databases and selected the `world` database
- Created a relational table named `country`
- Inserted multiple records representing country data
- Executed SQL queries with filtering conditions
- Retrieved query results matching specific criteria

**Goal:** Practice core SQL operations on an Aurora database.

---

## Key Lessons Learned
- Amazon Aurora is a fully managed, MySQL-compatible relational database
- Aurora databases are deployed within a VPC for secure access
- EC2 instances can act as database clients inside private networks
- MariaDB/MySQL clients are used to connect and query Aurora
- SQL can be used to create tables, insert records, and query data
- Managed databases reduce operational overhead

---

## Final Summary
This lab provided hands-on experience with:

- Creating and configuring an Amazon Aurora database
- Connecting securely from an Amazon EC2 instance
- Installing database client tools on Linux
- Executing SQL commands to manage and query data

These skills are fundamental for working with relational databases in cloud environments and are essential for cloud administration, backend development, and database management roles.

---

## Architecture Diagram


              ┌──────────────────────────┐
              │   User (AWS Console)     │
              │  Browser / Session Mgr  │
              └───────────▲──────────────┘
                          │
                          │ AWS Console
                          │
              ┌───────────┴─────────────┐
              │     Amazon EC2           │
              │     Command Host         │
              │  Linux + MariaDB Client │
              └───────────▲─────────────┘
                          │
                          │ Private Network
                          │
              ┌───────────┴─────────────┐
              │    Amazon Aurora         │
              │  MySQL-Compatible DB     │
              │  Writer Cluster Endpoint │
              └─────────────────────────┘
