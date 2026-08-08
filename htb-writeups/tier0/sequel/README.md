# HTB Starting Point — Sequel (MySQL/MariaDB Enumeration)

### **1. Service Discovery**

nmap -sV <target-ip>

**Purpose:** Discover open ports and identify the MySQL/MariaDB service version.

### **2. Connect to MySQL**

mysql -h <target-ip> -u root

If SSL error occurs:

mysql -h <target-ip> -u root --ssl=0

**Purpose:** Connect to the remote MySQL server.

### **3. Display Available Databases**

SHOW DATABASES;

**Purpose:** Lists all databases on the server.

### **4. Select a Database**

USE <database_name>;

**Example:**

USE htb;

**Purpose:** Switches to the selected database.

### **5. Display Tables**

SHOW TABLES;

**Purpose:** Lists all tables inside the selected database.

### **6. Display Table Structure**

DESCRIBE <table_name>;

or

DESC <table_name>;

**Example:**

DESCRIBE config;

**Purpose:** Shows column names, data types, keys, and attributes.

### **7. Display All Data from a Table**

SELECT * FROM <table_name>;

**Example:**

SELECT * FROM config;

**Purpose:** Retrieves all rows and columns.

### **8. Display Specific Columns**

SELECT username,password FROM users;

**Purpose:** Retrieves only the specified columns.

### **9. Count Records**

SELECT COUNT(*) FROM <table_name>;

**Example:**

SELECT COUNT(*) FROM users;

**Purpose:** Counts total records in a table.

### **10. Display Current Database**

SELECT DATABASE();

**Purpose:** Shows the currently selected database.

### **11. Display Current User**

SELECT USER();

**Purpose:** Shows the account currently connected.

### **12. Exit MySQL**

EXIT;

or

QUIT;

**Purpose:** Closes the MySQL session.

## **Typical HTB Workflow**

nmap -sV <target-ip>

mysql -h <target-ip> -u root --ssl=0

SHOW DATABASES;

USE htb;

SHOW TABLES;

DESCRIBE config;

SELECT * FROM config;

EXIT;

## **Important Commands to Remember**

| **Command** | **Purpose** |
| --- | --- |
| SHOW DATABASES; | List databases |
| USE dbname; | Select database |
| SHOW TABLES; | List tables |
| DESCRIBE table; | Show table structure |
| SELECT * FROM table; | Display all data |
| SELECT USER(); | Show current user |
| EXIT; | Exit MySQL |
