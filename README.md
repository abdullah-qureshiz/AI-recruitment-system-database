# AI Recruitment System — Coinbase Case Study

## 📌 Project Overview

The **AI Recruitment System** is a database project inspired by the case study *“How Coinbase Is Embracing AI in Recruiting.”*

The project is designed to organize recruitment data, manage candidates and job applications, track interviews, record hiring decisions, and support future AI-assisted candidate matching.

The system uses MySQL/MariaDB to store and manage recruitment information through a relational database.

## 🎯 Project Objectives

- Store and manage candidate information.
- Maintain job listings and department details.
- Track candidate applications and application statuses.
- Manage interviews and interview feedback.
- Record hiring decisions.
- Store candidate skills and job requirements.
- Support skill-based candidate matching.
- Store AI recommendation scores and explanations.
- Help make recruitment processes more organized and transparent.

## 🛠️ Technologies Used

- **Database:** MySQL / MariaDB
- **Database Management Tool:** phpMyAdmin
- **Local Development Environment:** XAMPP
- **Version Control:** Git and GitHub
- **Future Enhancement:** AI-based resume parsing and candidate matching

## 🗄️ Database Structure

The database currently contains **11 tables**.

| No. | Table Name | Description |
|---:|---|---|
| 1 | `candidates` | Stores candidate information, including names and contact details. |
| 2 | `jobs` | Stores job listings and related job information. |
| 3 | `applications` | Connects candidates to jobs and tracks application statuses. |
| 4 | `departments` | Stores department information. |
| 5 | `interviews` | Stores interview-related information. |
| 6 | `interviewfeedback` | Stores feedback from candidate interviews. |
| 7 | `hiringdecisions` | Stores hiring decisions for candidates. |
| 8 | `skills` | Stores skill names used in candidate matching. |
| 9 | `candidateskills` | Connects candidates with their skills. |
| 10 | `jobskills` | Connects jobs with their required skills. |
| 11 | `airecommendations` | Stores AI recommendation information, including match scores and explanations, according to its implemented structure. |

## 🔗 How the System Works

1. **Candidate Management:** Candidate details are stored in the `candidates` table.
2. **Job Management:** Available jobs and their related information are stored in the `jobs` table.
3. **Application Tracking:** The `applications` table links candidates to jobs and records application statuses.
4. **Skill Management:** The `skills`, `candidateskills`, and `jobskills` tables organize candidate skills and job requirements.
5. **Interview Management:** The `interviews` and `interviewfeedback` tables support interview tracking and feedback.
6. **Hiring Decisions:** The `hiringdecisions` table records recruitment outcomes.
7. **AI Recommendations:** The `airecommendations` table provides a place to store candidate match scores and recommendation explanations.

## 📊 Example SQL Queries

### 1. Display All Candidates

```sql
SELECT * FROM candidates;
```

### 2. Display All Jobs

```sql
SELECT * FROM jobs;
```

### 3. View Candidate Applications

This query combines candidate information, job titles, and application statuses.

```sql
SELECT
    candidates.full_name,
    jobs.job_title,
    applications.application_status
FROM applications
JOIN candidates
    ON applications.candidate_id = candidates.candidate_id
JOIN jobs
    ON applications.job_id = jobs.job_id;
```

### 4. Display All Skills

```sql
SELECT * FROM skills;
```

### 5. View AI Recommendations

```sql
SELECT * FROM airecommendations;
```

These queries demonstrate basic data retrieval and the use of SQL joins to combine information from related tables.

## ⚙️ How to Run the Project

### Step 1: Install the Required Software

Install XAMPP or another environment that supports MySQL/MariaDB, and open phpMyAdmin.

### Step 2: Create or Select the Database

The database shown in the current project is named `ai recruitment sys`.

To select it in SQL, use:

```sql
USE `ai recruitment sys`;
```

### Step 3: Import the Database

If you have an exported SQL database file:

1. Open phpMyAdmin.
2. Select the target database, or create it if necessary.
3. Open the **Import** tab.
4. Choose your `.sql` file.
5. Click **Import** or **Go**.

**Note:** Importing a full database backup may recreate tables and data. Use a test database if you do not want to overwrite existing information.

### Step 4: Verify the Tables

Run:

```sql
SHOW TABLES;
```

You should see the 11 tables listed in the database structure above.

### Step 5: Test the Queries

Open the SQL tab in phpMyAdmin and run the example queries to retrieve recruitment data.

## 🤖 AI Integration and Future Improvements

The current database provides a foundation for developing an AI-assisted recruitment system. Possible future improvements include:

- Resume parsing to extract candidate skills and experience.
- Comparing candidate skills with job requirements.
- Calculating skill-based match scores.
- Generating explanations for candidate recommendations.
- Tracking recommendation history.
- Interview scheduling and reminders.
- Recruitment reports and dashboards.
- Duplicate candidate detection.
- Data privacy and access controls.
- Human review of AI recommendations before final hiring decisions.

**Important:** Creating the `airecommendations` table does not itself implement AI. Actual AI recommendations require additional application logic, such as a backend service and an AI model or matching algorithm. The implementation of these features depends on the code and data added to the project.

## 🔐 Data Privacy and Responsible AI

A recruitment system should handle candidate information responsibly. Future development should consider:

- Restricting access to sensitive candidate data.
- Protecting stored personal information.
- Recording how recommendations are generated.
- Checking AI outputs for potential bias.
- Keeping final hiring decisions under human control.

## 📚 Learning Outcomes

Through this project, I am practicing:

- Relational database design.
- Creating and managing SQL tables.
- Using primary and foreign keys.
- Writing `SELECT` queries.
- Joining multiple tables.
- Organizing recruitment data.
- Designing a database structure for future AI integration.
- Managing a database using phpMyAdmin and XAMPP.

## 🚀 Future Scope

The project can be extended into a complete recruitment application with a user interface, backend APIs, resume upload functionality, automated skill matching, and reporting tools.

## ⚠️ Disclaimer

This is an educational database project inspired by a Coinbase recruitment case study. It is not an official Coinbase product and is not affiliated with or endorsed by Coinbase.

## 👨‍💻 Author

Developed as a learning project focused on database management and AI-assisted recruitment concepts.
