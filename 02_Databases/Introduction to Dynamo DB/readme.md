# Lab Summary: Introduction to Amazon DynamoDB

This lab demonstrated how to create, manage, and interact with an Amazon DynamoDB table using the AWS Management Console. It introduced DynamoDB as a fully managed NoSQL database service and showed how flexible schemas, primary keys, and efficient query operations support scalable cloud applications.

The lab focused on building a simple music library, adding and modifying items, retrieving data using queries and scans, and safely deleting the table at the end of the exercise.

---

## Working with Amazon DynamoDB Tables

### Accessing the AWS Management Console
- Accessed AWS through the lab environment
- Opened the AWS Management Console without changing the assigned Region
- Navigated to **Services → DynamoDB**

### Creating a DynamoDB Table
- Created a new table named **Music**
- Defined the primary key structure:
  - Partition key: **Artist** (String)
  - Sort key: **Song** (String)
- Used default settings for capacity and indexing
- Waited for the table status to change to **Active**

**Goal:** Understand how DynamoDB tables are created and how partition and sort keys uniquely identify items.

---

## Adding Data to the DynamoDB Table

- Added multiple items representing songs in a music library
- Each item included required attributes (Artist and Song)
- Additional attributes were added dynamically, including:
  - Album
  - Year
  - Genre
  - LengthSeconds
- Demonstrated that DynamoDB does not require a fixed schema and allows items to have different attributes

**Goal:** Demonstrate the flexibility of DynamoDB’s NoSQL data model.

---

## Modifying Existing Items

- Located items using the **Explore items** view
- Updated an existing item by correcting an attribute value
- Changed the release year of *Gangnam Style* from 2011 to 2012
- Saved changes directly in the DynamoDB console

**Goal:** Learn how to update data stored in a DynamoDB table.

---

## Querying and Scanning Data

### Query Operation
- Used the **Query** option to retrieve data using the primary key
- Queried the table using:
  - Artist: Psy
  - Song: Gangnam Style
- Retrieved the item quickly using indexed keys

### Scan Operation
- Used the **Scan** option to search across all items
- Applied a filter to find songs released in 1971
- Observed that scans are less efficient than queries

**Goal:** Understand the difference between query and scan operations and when to use each.

---

## Deleting the DynamoDB Table

- Selected the **Music** table from the DynamoDB dashboard
- Deleted the table using the **Delete table** action
- Confirmed deletion by typing `delete`
- Removed all data permanently by deleting the table

**Goal:** Practice proper cleanup of AWS resources after completing a lab.

---

## Key Lessons Learned
- Amazon DynamoDB is a fully managed NoSQL database service
- Tables require a partition key and optionally a sort key
- Items can have different attributes without a predefined schema
- Query operations are faster and more efficient than scan operations
- Deleting a table permanently removes all stored data

---

## Final Summary
This lab provided hands-on experience with:

- Creating and configuring DynamoDB tables
- Adding and modifying items with flexible attributes
- Retrieving data using queries and scans
- Managing and deleting AWS database resources

These skills are essential for building scalable, high-performance cloud applications using NoSQL databases on AWS.

---

## Architecture Diagram

              ┌──────────────────────────┐
              │      User Browser        │
              │  AWS Management Console  │
              └───────────▲──────────────┘
                          │ HTTPS
                          │
              ┌───────────┴─────────────┐
              │     Amazon DynamoDB      │
              │       Music Table        │
              │  Partition Key: Artist   │
              │  Sort Key: Song          │
              └─────────────────────────┘
