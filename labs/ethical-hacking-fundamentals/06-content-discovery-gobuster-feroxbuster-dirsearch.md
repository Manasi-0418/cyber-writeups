# EH6 — Website Content Discovery (Gobuster, Feroxbuster, Dirsearch)

## **1. Gobuster**

### **Introduction**

Gobuster is a command-line tool available in Kali Linux that is used to discover hidden directories, files, and subdomains associated with a website.

Many websites contain pages and folders that are not directly visible to users. Gobuster helps identify these hidden resources by testing names from a wordlist.

### **Purpose**

- Discover hidden directories

- Identify hidden files

- Find publicly accessible resources

- Discover subdomains

- Understand website structure

### **Features**

- Fast scanning

- Simple command-line interface

- Supports directory discovery

- Supports subdomain discovery

- Uses custom wordlists

### **Common Parameters**

- dns → DNS mode

- -d → Domain Name

- -w → Wordlist

### **Observation**

Gobuster identified hidden resources associated with the target website and helped improve understanding of the website structure.

## **2. Feroxbuster**

### **Introduction**

Feroxbuster is a fast content discovery tool used to identify publicly accessible directories, files, and web resources.

It is commonly used during web application reconnaissance and security assessments.

### **Purpose**

- Discover hidden directories

- Identify publicly accessible resources

- Understand website structure

- Support information gathering activities

### **Working Principle**

Feroxbuster works by:

- Taking a target URL.

- Using a wordlist.

- Sending HTTP requests.

- Analyzing responses.

- Recursively exploring discovered directories.

-u for url

-w for wordlists

### **Ex- **Target Website:-[https://www.youtube.com](https://www.youtube.com/)/

Command:-feroxbuster -u [https://www.youtube.com](https://www.youtube.com/)/

### Directory Brute Force:

### feroxbuster -u[ ](https://www.youtube.com/)[https://www.youtube.com/](https://www.youtube.com/)  -w /usr/share/wordlists/dirb/common.txt

### **Observation**

Feroxbuster identified multiple publicly accessible paths and resources associated with the target website.

Output you will given:

200 GET /admin

200 GET /login

403 GET /backup

301 GET /images

### **Important File Extensions**

While analyzing results, commonly observed file types may include:

- .env

- .config

- .git

- .js

- .php

- .cgi

### **Advantages**

- Fast scanning

- Recursive discovery

- Easy to use

- Useful for reconnaissance

### **Limitations**

- Depends on wordlist quality

- May generate many requests

- Results require verification

## **3. ExifTool**

### **Introduction**

ExifTool is a metadata analysis tool used to read, write, and edit metadata contained within files.

Metadata refers to information stored inside a file that may not be immediately visible.

### **Information Revealed**

- Author Information

- Creation Date

- Modification Date

- Device Information

- Software Information

- Location Information (if available)

### **Applications**

- Information Gathering

- Digital Forensics

- Open Source Intelligence (OSINT)

- Security Research

### **Example Metadata**

A photograph may contain:

- Camera Model

- Date Created

- Resolution Information

- Software Used

### **Observation**

ExifTool successfully extracted metadata from the selected file and displayed information useful for analysis.

### **Advantages**

- Easy to use

- Supports multiple file formats

- Useful for investigations

- Detailed metadata analysis

### **Limitations**

- Some files may not contain metadata

- Metadata can be removed or modified

## **4. Dirsearch**

### **Introduction**

Dirsearch is a Python-based tool used to discover hidden directories and files on web applications.

It works by sending requests using entries from a wordlist and identifying existing paths on a website.

Dirsearch helps to:

- Discover hidden folders (e.g., /admin, /backup)

- Find sensitive files (e.g., .php, .zip, .bak )

- Identify attack surfaces in web applications

- Support bug bounty and penetration testing.

### **Purpose**

- Discover hidden directories

- Identify publicly accessible files

- Understand web application structure

- Support reconnaissance activities

### **Features**

- Easy to use

- Flexible configuration

- Suitable for beginners and professionals

- Supports multiple file extensions

### **Simple Understanding**

Dirsearch works by testing multiple directory and file names from a wordlist and identifying resources that exist on the target website.

### **Example**

Target Website:[http://zero.webappsecurity.com/](http://zero.webappsecurity.com/)

Command - dirsearch -u http://zero.webappsecurity.com/

### **Using wordlists**

### dirsearch -u[ ](http://zero.webappsecurity.com/)[http://zero.webappsecurity.com/](http://zero.webappsecurity.com/) -w/usr/share/wordlists/dirb/common.txt

###  Observation**

Dirsearch successfully identified multiple accessible directories and files associated with the target website.

### **Advantages**

- Easy to use

- Flexible options

- Good reporting

- Useful for web reconnaissance

### **Limitations**

- Depends on wordlist quality

- May miss uncommon paths

- Large scans may take additional time

## **Conclusion**

Gobuster, Feroxbuster, ExifTool, and Dirsearch are useful tools for information gathering and website analysis. These tools help identify publicly accessible resources, understand website structure, analyze metadata, and collect information that supports security assessments and reconnaissance activities.
