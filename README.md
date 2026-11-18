# MySQL Assignment 1 – DDL Commands & Constraints

This repository contains the complete SQL script solutions for **MySQL Assignment 1: DDL Commands & Constraints**.

---

## Database Schema

The database `employee` consists of three relational tables:
1. **departments**: Stores department details (`department_id`, `department_name`).
2. **location**: Stores branch location details (`location_id`, `location`).
3. **employees**: Stores employee records linked to departments and locations.

---

## Tasks Implemented

### 1. DDL Commands
- **Table Creation (`CREATE`)**: Built the `employee` database along with `departments`, `location`, and `employees` tables according to the schema.
- **Table Alteration (`ALTER`)**:
  - Added new column `email` to `employees`.
  - Modified data type of `designation` to `VARCHAR(255)`.
  - Dropped the `age` column from `employees`.
  - Renamed column `hire_date` to `date_of_joining`.
- **Table Renaming (`RENAME`)**:
  - Renamed `departments` to `departments_info`.
  - Renamed `location` to `locations`.
- **Table Truncation (`TRUNCATE`)**: Emptied records from `employees` while retaining structure.
- **Dropping (`DROP`)**: Dropped the `employees` table and `employee` database.

---

### 2. Constraints & Database Recreation
Recreated the `employee` database with strict schema integrity constraints:
- **`departments`**:
  - `department_id`: `PRIMARY KEY`
  - `department_name`: `NOT NULL UNIQUE`
- **`location`**:
  - `location_id`: `AUTO_INCREMENT PRIMARY KEY`
  - `location`: `NOT NULL UNIQUE`
- **`employees`**:
  - `employee_id`: `PRIMARY KEY`
  - `employee_name`: `NOT NULL`
  - `gender`: `ENUM('M', 'F')`
  - `age`: `CHECK (age >= 18)`
  - `hire_date`: `DEFAULT (CURRENT_DATE)`
  - `department_id`: `FOREIGN KEY` referencing `departments(department_id)`
  - `location_id`: `FOREIGN KEY` referencing `location(location_id)`
