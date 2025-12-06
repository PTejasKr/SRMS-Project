PROJECT OVERVIEW
----------------
A console-based Student Record Management System written in C that provides
comprehensive functionality for managing student records with role-based
access control.

FEATURES
--------
* Role-Based Access Control (Admin, Staff, Guest)
* Complete CRUD operations for student records
* Advanced search functionality (ID, Name, Program, Status)
* Data export to text format
* Automatic backup creation
* CSV-based data persistence
* Sample data generation
* Audit trail (created/modified dates and users)

SYSTEM REQUIREMENTS
-------------------
* C Compiler (GCC recommended)
* Standard C libraries
* Operating System: Windows/Linux/MacOS
* Minimum RAM: 512 MB
* Disk Space: 10 MB (for program and data files)

COMPILATION
-----------
Using GCC:
    gcc -o student_system main.c -std=c99

Using other compilers, ensure C99 standard support or later.

FILE STRUCTURE
--------------
* main.c                    - Main source code
* students.csv              - Primary data file (auto-generated)
* students_export.txt       - Export file (generated on export)
* students_backup_*.csv     - Backup files (timestamped)

DATA FILE FORMAT
----------------
The system uses CSV format with the following fields:
- s_ID: Student ID (auto-generated, format: SYYYY-NNNNN)
- full_name: Student's full name
- dob: Date of birth
- gender: Gender
- contact: Contact number
- email: Email address
- address: Physical address
- emergency_contact: Emergency contact information
- enrollment_date: Date of enrollment
- program: Academic program/course
- year: Current academic year
- semester: Current semester
- status: Status code (0=Active, 1=Inactive, 2=Graduated, 3=Suspended)
- created_date: Record creation timestamp
- modified_date: Last modification timestamp
- created_by: User who created the record
- modified_by: User who last modified the record

USER ROLES & PERMISSIONS
-------------------------
1. ADMIN (Full Control)
   - Add new students
   - Delete students
   - Update student records
   - Search and view records
   - Export data
   - Create backups
   - Generate sample data

2. STAFF (Limited Control)
   - Update student records
   - Search and view records
   - Display student lists

3. GUEST (Read-Only)
   - Search and view records
   - Display student lists

HOW TO USE
----------
1. Run the compiled program
2. Select your role (Admin/Staff/Guest)
3. Navigate through the menu using numeric options
4. Follow on-screen prompts for each operation

MENU OPTIONS
------------
Admin Menu:
  1. Add new student
  2. Delete student
  3. Update student
  4. Search students
  5. List students
  6. View student by ID
  7. Save and Log out
  8. Export/Backup/Sample data utilities
  9. Help/Instructions
  0. Exit without saving

Staff Menu:
  1. Display List
  2. Search Students
  3. View student by ID
  4. Update student
  5. Help/Instructions
  0. Log out

Guest Menu:
  1. Display List
  2. Search Students
  3. View student by ID
  4. Help/Instructions
  0. Log out

SEARCH OPTIONS
--------------
1. By Student ID - Exact match search
2. By Name - Partial/full name search (case-insensitive)
3. By Program - Search by academic program
4. By Status - Filter by student status

IMPORTANT NOTES
---------------
* Maximum students supported: 20,000 records
* Student IDs are auto-generated in format: SYYYY-NNNNN
  (where YYYY = current year, NNNNN = 5-digit sequential number)
* Data is automatically saved after each add/update/delete operation
* Commas in names and addresses are automatically replaced with semicolons
  to maintain CSV format integrity
* Use "Save and Log out" option in Admin menu to ensure data persistence
* Backup files are timestamped for easy identification

DATA SAFETY
-----------
* Always create backups before major operations
* The system replaces commas in text fields to prevent CSV corruption
* Use the backup utility regularly
* Export data periodically for additional safety

TROUBLESHOOTING
---------------
Issue: "Failed to open data file"
Solution: Ensure the program has read/write permissions in its directory

Issue: "Storage full"
Solution: Maximum capacity (20,000 records) reached. Consider archiving
          old records or increasing MAX_STUDENTS constant and recompiling

Issue: Student ID already exists
Solution: This should not occur with auto-generated IDs. If it does,
          check for data file corruption

LIMITATIONS
-----------
* Maximum 20,000 student records
* No password authentication (role selection only)
* Single-user system (no concurrent access)
* Basic validation on input fields
* CSV format limitations for special characters

FUTURE ENHANCEMENTS
-------------------
* Password-protected user authentication
* Multi-user concurrent access with database backend
* Advanced reporting and analytics
* GPA tracking and grade management
* Course enrollment management
* Photo/document attachment support
* Email notifications
* Web-based interface
