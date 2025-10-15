#Data Dictionary
This document details the structure,columns,data types and constraints for all tables in the project's **Supabase** database schema.
# Data Dictionary

## Table: students

| Column Name | Data Type | Nullable | Constraints | Description |
| :--- | :--- | :---: | :--- | :--- |
| **student_id** | `UUID` | No | **PRIMARY KEY** | Unique identifier for the student record. |
| **first_name** | `VARCHAR(50)` | No | NOT NULL | The student's legal first name. |
| **email** | `TEXT` | No | UNIQUE | Student's primary email address. Prevents duplicate accounts. |
| **created_at** | `TIMESTAMPTZ`| No | DEFAULT NOW() | Timestamp recording when the record was created. |
---## Table: enrollments

| Column Name | Data Type | Nullable | Constraints | Description |
| :--- | :--- | :---: | :--- | :--- |
| **enrollment_id** | `UUID` | No | **PRIMARY KEY** | Unique ID for the enrollment instance. |
| **student_id** | `UUID` | No | **FOREIGN KEY** (references `students`) | Links to the enrolled student. **MANDATORY** Foreign Key. |
| **course_id** | `UUID` | No | **FOREIGN KEY** (references `courses`) | Links to the course being taken. **MANDATORY** Foreign Key. |
| **enrollment_date**| `DATE` | No | | The date the student was officially enrolled. |
