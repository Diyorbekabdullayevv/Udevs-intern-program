# Data Model Documentation

## Overview

This document describes the full database schema for the Task Management System, including all tables, fields, relationships, and notes on design decisions.

---

## 1. Tables and Fields

### **1.1 projects**

Purpose: Stores all projects in the system.

| Field       | Type      | Constraints        | Description                   |
| ----------- | --------- | ------------------ | ----------------------------- |
| id          | integer   | PK, auto-increment | Unique project ID             |
| name        | varchar   | NOT NULL           | Project name                  |
| description | text      | NULL allowed       | Optional project description  |
| start_date  | datetime  | NULL allowed       | Project start date (optional) |
| end_date    | datetime  | NULL allowed       | Project end date (optional)   |
| status_id   | integer   | NOT NULL, FK       | Project status                |
| created_at  | timestamp | NOT NULL           | Creation timestamp            |
| created_by  | integer   | NOT NULL, FK       | User who created the project  |

---

### **1.2 tasks**

Purpose: Stores all tasks linked to projects.

| Field       | Type     | Constraints        | Description           |
| ----------- | -------- | ------------------ | --------------------- |
| id          | integer  | PK, auto-increment | Unique task ID        |
| project_id  | integer  | NOT NULL, FK       | Related project       |
| title       | varchar  | NOT NULL           | Task title            |
| description | text     | NULL allowed       | Task description      |
| priority_id | integer  | NOT NULL, FK       | Linked priority value |
| status_id   | integer  | NOT NULL, FK       | Linked status value   |
| due_date    | datetime | NULL allowed       | Optional due date     |
| user_id     | integer  | NOT NULL, FK       | Assigned user         |

---

### **1.3 users**

Purpose: Stores all users of the system.

| Field       | Type    | Constraints      | Description                 |
| ----------- | ------- | ---------------- | --------------------------- |
| id          | integer | PK               | Unique user ID              |
| email       | varchar | UNIQUE, NOT NULL | User email                  |
| name        | varchar | NOT NULL         | Full name                   |
| password    | varchar | NOT NULL         | Hashed password             |
| client_type | varchar | NOT NULL         | Ucode-specific field        |
| role        | varchar | NOT NULL         | User role (Admin, PM, etc.) |

---

### **1.4 task_comments**

Purpose: Stores comments made on tasks.

| Field      | Type      | Constraints        | Description                |
| ---------- | --------- | ------------------ | -------------------------- |
| id         | integer   | PK, auto-increment | Comment ID                 |
| task_id    | integer   | NOT NULL, FK       | Related task               |
| comment    | text      | NOT NULL           | Comment body               |
| created_at | timestamp | NOT NULL           | Time of comment            |
| created_by | integer   | NOT NULL, FK       | User who wrote the comment |

---

### **1.5 task_status**

Purpose: Lookup table for statuses ("Todo", "In Progress", "Done").

| Field  | Type    | Constraints | Description |
| ------ | ------- | ----------- | ----------- |
| id     | integer | PK          | Status ID   |
| status | varchar | NOT NULL    | Status name |

---

### **1.6 task_priority**

Purpose: Lookup table for priorities ("Low", "Medium", "High").

| Field    | Type    | Constraints | Description   |
| -------- | ------- | ----------- | ------------- |
| id       | integer | PK          | Priority ID   |
| priority | varchar | NOT NULL    | Priority name |

---

### **1.7 project_members**

Purpose: Defines which users are members of a given project.

| Field      | Type    | Constraints  | Description     |
| ---------- | ------- | ------------ | --------------- |
| project_id | integer | NOT NULL, FK | Related project |
| user_id    | integer | NOT NULL, FK | Related user    |

*Composite primary key:* (project_id, user_id)

---

## 2. Relationships

### **projects → task_status**

projects.status_id → task_status.id

### **projects → users**

projects.created_by → users.id

### **tasks → projects**

tasks.project_id → projects.id

### **tasks → task_status**

tasks.status_id → task_status.id

### **tasks → task_priority**

tasks.priority_id → task_priority.id

### **tasks → users**

tasks.user_id → users.id

### **task_comments → tasks**

task_comments.task_id → tasks.id

### **task_comments → users**

task_comments.created_by → users.id

### **project_members → users & projects**

project_members.project_id → projects.id
project_members.user_id → users.id

---

## 3. Design Decisions

### **Nullable vs. Non-nullable**

* Project start/end dates are optional because some projects begin without finalized schedules.
* Due dates can be optional depending on workflow.
* Most foreign keys are NOT NULL to enforce data integrity.

### **Lookup Tables**

Statuses and priorities are stored in separate tables to:

* Prevent hardcoding values
* Support dynamic customization
* Maintain clean separation

### **Project Members Table**

A junction table allows:

* Many users to join many projects
* Enforcing membership rules

### **Timestamps**

Always non-null for tracking and auditing.

---

## 4. Diagram File

Stored at:
`diagrams/data-model.png`

---

## 5. Summary

This schema supports:

* Complete project/task management
* Multi-user collaboration
* Role-based access
* Extensibility for future features

If you need the SQL migration version, ERD diagrams, or improvements—just ask.
