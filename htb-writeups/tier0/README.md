# HTB Starting Point — Redeemer (Redis Enumeration)

### **1. Service Discovery with Nmap**

nmap -sV <target-ip>

**Purpose:**

- Identifies open ports on the target.

- Detects the service running on each port and its version.

**Example Output:**

6379/tcp open redis Redis key-value store

This indicates that Redis is running on port **6379**.

### **2. Connecting to the Redis Server**

redis-cli -h <target-ip>

**Purpose:**

- Connects to a remote Redis server.

- -h specifies the target host.

**Example:**

redis-cli -h 10.129.72.14

### **3. Retrieving Server Information**

INFO

**Purpose:**

- Displays detailed information about the Redis server.

- Includes version, memory usage, connected clients, uptime, and more.

### **4. Viewing Database Information**

INFO keyspace

**Purpose:**

- Shows available databases and the number of keys stored in each.

**Example Output:**

db0:keys=4

This means database **0** contains **4 keys**.

### **5. Selecting a Database**

SELECT <database-number>

**Purpose:**

- Switches to a specific Redis database.

**Example:**

SELECT 0

Redis uses database **0** by default.

### **6. Counting Keys in the Current Database**

DBSIZE

**Purpose:**

- Returns the total number of keys stored in the currently selected database.

**Example Output:**

(integer) 4

### **7. Listing All Keys**

KEYS *

**Purpose:**

- Displays all keys stored in the current database.

**Example Output:**

1) flag

2) user

3) temp

### **8. Identifying a Key's Data Type**

TYPE <key-name>

**Purpose:**

- Determines the data type of a specific key.

**Example:**

TYPE flag

**Possible Results:**

string

hash

list

set

zset

### **9. Retrieving a String Value**

GET <key-name>

**Purpose:**

- Retrieves the value of a key whose type is **string**.

**Example:**

GET flag

**Output:**

"03e1d2b376c37ab3f5319922053953eb"

## **Complete Enumeration Workflow**

nmap -sV <target-ip>

redis-cli -h <target-ip>

INFO

INFO keyspace

SELECT 0

DBSIZE

KEYS *

TYPE flag

GET flag

### **Key Learning Points**

- **Nmap** is used to discover services.

- **Redis runs by default on port 6379.**

- **redis-cli** is the Redis command-line client.

- **INFO** provides server details.

- **SELECT** switches between databases.

- **DBSIZE** counts keys.

- **KEYS ** enumerates all keys.

- **TYPE** identifies the data structure of a key.

- **GET** retrieves the value of a string key.

These commands form a basic Redis enumeration methodology useful for HTB labs, penetration testing practice, and Redis administration.
