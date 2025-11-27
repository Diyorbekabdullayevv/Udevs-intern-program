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
| name        | string    | NOT NULL           | Project name                  |
| description | text      | NULL allowed       | Optional project description  |
| start_date  | date      | NULL allowed       | Project start date (optional) |
| end_date    | date      | NULL allowed       | Project end date (optional)   |
| status_id   | integer   | NOT NULL, FK       | Project status                |
| created_by  | integer   | NOT NULL, FK       | User who created the project  |
| created_at  | datetime  | NULL allowed       | Creation date and time        |
| updated_at  | datetime  | NULL allowed       | Updated date and time         |

---

### **1.2 tasks**

Purpose: Stores all tasks linked to projects.

| Field               | Type     | Constraints        | Description           |
| ------------------- | -------- | ------------------ | --------------------- |
| id                  | integer  | PK, auto-increment | Unique task ID        |
| title               | string   | NOT NULL           | Task title            |
| description         | text     | NULL allowed       | Task description      |
| project_id          | integer  | NOT NULL, FK       | Related project       |
| assigned_to         | integer  | NULL allowed, FK   | Task assigned user    |
| created_by          | integer  | NULL allowed, FK   | Task created user     |
| status_id           | integer  | NULL allowed, FK   | Linked status value   |
| priority_id         | integer  | NULL allowed, FK   | Linked priority value |
| due_date            | date     | NULL allowed       | Optional due date     |
| estimated_hours     | decimal  | NULL allowed       | Estimated hours       |
| completed_at        | datetime | NULL allowed       | Task completion date  |
| created_at          | datetime | NULL allowed       | Task creation date    |
| updated_at          | datetime | NULL allowed       | Task updated date     |

---

### **1.3 users**

Purpose: Stores all users of the system.

| Field       | Type    | Constraints      | Description                 |
| ----------- | ------- | ---------------- | --------------------------- |
| id          | integer | PK               | Unique user ID              |
| name        | string  | NOT NULL         | Full name                   |
| email       | string  | UNIQUE           | User email                  |
| login       | string  | NULL allowed     | User login                  |
| password    | string  | NOT NULL         | Hashed password             |
| client_type | string  | NULL allowed     | Ucode-specific field        |
| role        | string  | NULL allowed     | User role (Admin, PM, etc.) |

---

### **1.4 task_comments**

Purpose: Stores comments made on tasks.

| Field      | Type      | Constraints        | Description                |
| ---------- | --------- | ------------------ | -------------------------- |
| id         | integer   | PK, auto-increment | Comment ID                 |
| task_id    | integer   | NOT NULL, FK       | Related task               |
| user_id    | integer   | NOT NULL, FK       | Related user               |
| comment    | text      | NOT NULL           | Comment body               |
| created_at | datetime  | NULL allowed       | Time of comment            |
| created_by | integer   | NULL allowed       | User who wrote the comment |

---

### **1.5 task_status**

Purpose: Lookup table for statuses ("Todo", "In Progress", "Done").

| Field  | Type    | Constraints  | Description  |
| ------ | ------- | ------------ | ------------ |
| id     | integer | PK           | Status ID    |
| name   | string  | NULL allowed | Status name  |
| slug   | string  | NULL allowed | Status slug  |
| color  | string  | NULL allowed | Status color |

---

### **1.6 task_priority**

Purpose: Lookup table for priorities ("Low", "Medium", "High").

| Field    | Type    | Constraints  | Description    |
| -------- | ------- | ------------ | -------------- |
| id       | integer | PK           | Priority ID    |
| name     | string  | NULL allowed | Priority name  |
| slug     | string  | NULL allowed | Priority slug  |
| priority | integer | NULL allowed | Priority order |

---

### **1.7 project_members**

Purpose: Defines which users are members of a given project.

| Field      | Type     | Constraints  | Description     |
| ---------- | -------- | ------------ | --------------- |
| id         | integer  | PK           | ID              |
| project_id | integer  | NOT NULL, FK | Related project |
| user_id    | integer  | NOT NULL, FK | Related user    |
| role       | string   | NULL allowed | Member role     |
| added_at   | datetime | NULL allowed | Added time      |
*Composite primary key:* (project_id, user_id)

---

## 2. Relationships


## 1. Projects table relations:

### **projects → task_status**
projects.status_id → task_status.id

### **projects → users**
projects.created_by → users.id

## 2. Tasks table relations:

### **tasks → projects**
tasks.project_id → projects.id

### **tasks → users**
tasks.assigned_to → users.id

### **tasks → users**
tasks.created_by → users.id

### **tasks → task_status**
tasks.status_id → task_status.id

### **tasks → task_priority**
tasks.priority_id → task_priority.id

## 3. Task comments table relations:

### **task_comments → tasks**
task_comments.task_id → tasks.id

### **task_comments → users**
task_comments.user_id → users.id

## 4. Project members table relations:

### **project_members → projects**
project_members.project_id → projects.id

### **project_members → users**
project_members.user_id → users.id

---

## 3. Design Decisions

### **Nullable vs. Non-nullable**

* Project start/end dates are optional because some projects begin without finalized schedules.
* Due dates can be optional depending on workflow.
* Most foreign keys are          to enforce data integrity.

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
`screenshots/data-model.png`

---

## 5. Summary

This schema supports:

* Complete project/task management
* Multi-user collaboration
* Role-based access
* Extensibility for future features
