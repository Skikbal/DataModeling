# 📘 Introduction to Relational Databases


## 🧩 Overview of Database Types

* **Relational vs. NoSQL Databases**

  * These two types of databases handle **data modeling differently**.
  * Understanding each helps determine the right modeling approach for your data needs.

---

## 🗃️ What is a Relational Database?

* Based on the **relational model** developed by **Edgar Codd at IBM** in the late 1960s–early 1970s.
* Organizes data into **tables (relations)** made up of **rows (tuples)** and **columns (attributes)**.
* **Each table represents an entity**, such as customers or products.
* **Each row is uniquely identified** by a **primary key**.

---

## 🛠️ What is an RDBMS?

* **RDBMS** = Relational Database Management System

  * Software that stores, manages, and queries relational databases.
  * Uses **SQL (Structured Query Language)** for defining, manipulating, and querying data.
* Common RDBMS platforms:

  * **Oracle** – Enterprise-grade, widely used in banking and large systems.
  * **Teradata** – Focused on large-scale data warehousing.
  * **MySQL** – Open-source, widely used in web development.
  * **PostgreSQL** – Advanced open-source RDBMS with rich features.
  * **SQLite** – Lightweight, file-based DB used in small/local apps.
  * **Microsoft SQL Server** – Popular in enterprise Windows environments.

---

## 🔍 Key Components

* **Database (or Schema):**

  * A collection of related tables.
* **Table (Relation):**

  * A grid of **columns** (attributes) and **rows** (tuples).
  * Each row represents a data record.
* **Example: Customer Table**

  | Name   | Email                                     | City |
  | ------ | ----------------------------------------- | ---- |
  | Amanda | [janedoe@xyz.com](mailto:janedoe@xyz.com) | NYC  |

---

## ✅ Why It Matters

* Relational data models ensure **consistency**, **integrity**, and **efficient querying**.
* Proper modeling helps **simplify queries** and supports **scalable, reliable applications**.
* **SQL knowledge** is essential for working with relational databases effectively.

---

Here’s a **README-style summary in bullet points** for the **Advantages of Using a Relational Database**:

---

# ✅ Advantages of Using a Relational Database

---

## 🔧 Flexibility & Query Power

* **Flexible SQL Querying**

  * Powerful and versatile for querying, updating, and managing data.

* **Focus on Modeling the Data**

  * Design is centered around the data structure, not individual queries.

---

## 🔗 Data Relationships & Analysis

* **Support for JOINS**

  * Easily relate data across multiple tables.

* **Built-in Aggregations & Analytics**

  * Perform complex calculations, summaries, and grouping operations directly in SQL.

* **Secondary Indexes**

  * Improve performance for queries on non-primary key columns.

---

## 📦 Data Integrity & Reliability

* **Smaller Data Volumes**

  * Optimized for structured data with predefined schema.

* **ACID Transactions Support**

  * Ensures data **Atomicity**, **Consistency**, **Isolation**, and **Durability** — crucial for critical systems (e.g., finance, healthcare).

---

## 🔄 Adaptability

* **Easier to Adapt to Business Requirements**

  * Schema changes (e.g., adding columns, modifying tables) can be done with relative ease compared to some NoSQL systems.

---

# 🔒 Introduction to ACID Transactions

**ACID** stands for **Atomicity**, **Consistency**, **Isolation**, and **Durability** — four essential properties that ensure **reliable, error-free transactions** in relational databases.

ACID transactions are especially critical in systems like **banking**, **finance**, and **e-commerce**, where data integrity is non-negotiable.

---

## ⚙️ What is a Transaction?

* A **transaction** is a group of one or more database operations treated as a **single logical unit**.
* ACID ensures the transaction either **completes fully** or **does not occur at all**, protecting data from corruption in case of system failure or interruption.

---

## 🧪 ACID Properties Explained

### 🔹 **Atomicity**

* **"All or nothing"** rule — either the entire transaction happens, or none of it does.
* Example: Transferring money from Checking ➡️ Savings — both debit and credit must happen together, or not at all.

### 🔹 **Consistency**

* Only valid data (that adheres to defined **constraints and rules**) can be saved.
* Example: If a column accepts only `TRUE/FALSE`, trying to insert `"Hello"` will fail, and the database remains unchanged.

### 🔹 **Isolation**

* Each transaction runs **independently**, even if executed concurrently.
* Data is **locked** during a transaction to prevent interference.
* Ensures correct results as if transactions were run **sequentially**.

### 🔹 **Durability**

* Once a transaction is **committed**, its changes are **permanently recorded**, even in case of power loss or crashes.
* Uses **non-volatile storage** to persist data.

---

## 🛡️ Why ACID Matters

* Ensures **data integrity**, **accuracy**, and **reliability**.
* Prevents:

  * Incomplete operations
  * Data corruption
  * Conflicts between concurrent users
* Essential for mission-critical systems (e.g., banking, healthcare, inventory)

---

ACID transactions are a foundational concept in relational databases and a major reason they remain trusted for **high-integrity data systems**.

---

Here’s a **README-style summary in bullet points** for **When *Not* to Use a Relational Database**:

---

# ⚠️ When *Not* to Use a Relational Database


## 🚫 Limitations of Relational Databases

While relational databases are powerful and reliable, there are scenarios where they may not be the best fit.

---

## ❌ Avoid RDBMS If You Need:

### 📊 **Massive Data Volume or Diverse Data Formats**

* Not designed to handle **very large-scale** data or **varied formats** (e.g., JSON, unstructured logs).
* Struggles with **heterogeneous and complex data**.

### 🐌 **High Throughput / Fast Reads & Writes**

* ACID compliance ensures reliability, but **slows down performance** under heavy load.
* Poor fit for use cases that demand **real-time or near-real-time performance**.

### 🧱 **Flexible Schema**

* Relational databases require **strict schemas**.
* Cannot easily accommodate dynamic or sparse data structures.
* Not ideal when you need to **add new fields frequently** or **store data with missing values**.

### 📉 **Limited Scalability**

* Relational DBs scale **vertically only** — by upgrading server hardware.
* Cannot scale **horizontally** by adding more machines like NoSQL systems can.

### 🛑 **Single Point of Failure**

* Typically rely on a **centralized architecture (coordinator-worker)**.
* If the main node fails, a **manual failover** or delay occurs, reducing **availability**.

---

## ✅ Better Alternatives for These Needs

If your system requires:

* 🌐 **High availability** (always on, minimal downtime)
* 📈 **Horizontal scalability** (adding servers = more capacity)
* 🧮 **Flexible schemas**
* 🚀 **High read/write speeds at scale**

> Consider using a **NoSQL database** like MongoDB, Cassandra, or DynamoDB.
