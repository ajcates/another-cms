# Database Schema

This document defines the database schema for the project.

## Tables

[List and describe the database tables, including the columns, data types, and relationships.]

### Example Table: `users`

| Column | Data Type | Constraints |
| --- | --- | --- |
| id | INT | PRIMARY KEY |
| username | VARCHAR(255) | NOT NULL, UNIQUE |
| email | VARCHAR(255) | NOT NULL, UNIQUE |
| created_at | TIMESTAMP | DEFAULT CURRENT_TIMESTAMP |
