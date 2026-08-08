# EH4 — Information Gathering: Domain and Subdomain Analysis

## **1. Introduction**

Information Gathering is the process of collecting information about a target website or domain before performing any security assessment. It helps security professionals understand the target environment without directly interacting with the system.

Domain and Subdomain Analysis is an important part of information gathering because it provides details about website ownership, DNS records, hosting information, and publicly accessible services.

### **Goals**

- Identify domain information

- Discover IP addresses

- Find DNS records

- Identify subdomains

- Analyze historical website data

- Understand hosting infrastructure

## **2. WHOIS Lookup (Domain Information)**

### **What is WHOIS?**

WHOIS is a service used to obtain information about a registered domain name. It provides registration and ownership details of a domain.

### **Tools Used**

- DomainTools WHOIS Lookup -whois.domaintools.com 

- Online WHOIS Services

### **Information Obtained**

- Domain Name

- Registration Date

- Expiry Date

- Registrar Information

- Name Servers

- Domain Status

### **Procedure**

Step 1:
Select a target domain.

Example:

[facebook.com](http://facebook.com)

Step 2:
Open a WHOIS lookup tool.

Step 3:
Enter the domain name and click Search.

Step 4:
Review the information displayed by the tool.

### **Observation**

The WHOIS lookup displayed registration details, registrar information, and name server records associated with the domain.

## **3. DNS Records Information**

### **What is DNS?**

DNS (Domain Name System) converts domain names into IP addresses and helps users access websites using human-readable names.

### **Common DNS Records**

| **Record Type** | **Purpose** |
| --- | --- |
| A Record | Maps a domain to an IPv4 address |
| AAAA Record | Maps a domain to an IPv6 address |
| MX Record | Specifies mail servers |
| NS Record | Specifies authoritative name servers |
| TXT Record | Used for verification and security information |

### **Importance of DNS Records**

DNS records help identify infrastructure components associated with a website and provide information about communication services.

## **4. Wayback Machine (Historical Website Analysis)**

### **Tool Used**

Internet Archive Wayback Machine

### **Purpose**

The Wayback Machine stores historical versions of websites and allows users to view previous website designs and content.

### **Benefits**

- View old versions of websites

- Identify historical changes

- Discover removed pages

- Analyze website evolution

### **Procedure**

Step 1:
Open the Wayback Machine website.

Step 2:
Enter the target domain.

Step 3:
Select an available year and date.

Step 4:
View the archived version of the website.

### **Observation**

The archived snapshots displayed older versions of the website and highlighted changes made over time.

## **5. Finding Host and IP Address using linux command**

Host and IP address information can be obtained using Linux networking tools.

### **Tools Used**

- host

- nslookup

- ping

### **Example Commands**

host facebook.com

### **Description**

The host command displays IP address information related to the domain.

The whois command displays registration and ownership information associated with the domain.

### **Observation**

The command output displayed IP address information and domain-related details.

## **6. Subdomain Enumeration**

### **What is a Subdomain?**

A subdomain is a child domain that exists under a main domain.

### **Example**

Main Domain:

[google.com](http://google.com)

Subdomains:

- mail.google.com

- maps.google.com

### **Importance**

Subdomain enumeration helps identify publicly accessible services associated with a website.

### **Observation**

Several publicly available subdomains were identified under the target domain.

## **7. Subfinder Tool**

### **Introduction**

Subfinder is a subdomain discovery tool commonly used in Kali Linux.

### **Example Command**

subfinder -d facebook.com | tee -a facebook.txt

-a à append (add data instead of overwrite)

tee à save à show output

-d stands for domain 

### **Description**

The tool collects publicly available subdomain information related to the target domain.

### **Observation**

The tool successfully identified multiple subdomains associated with the target domain.

## **8. Sublist3r Tool**

### **Introduction**

Sublist3r is a subdomain enumeration tool that collects subdomain information from multiple public sources.

### **Example Command**

Sublist3r -d [google.com](http://google.com)

### **Observation**

The tool identified additional subdomains that may not have been discovered through other methods.

## **9. Counting Subdomains**

The total number of discovered subdomains can be calculated using Linux commands.

### **Example Command**

cat facebook.txt | wc -l

### **Description**

- cat → Displays file contents

- wc -l → Counts the number of lines

### **Observation**

The output displayed the total number of discovered subdomains.

**Screenshot:**
*(Insert Counting Output Screenshot Here)*

## **Why is Subdomain Enumeration Important?**

- Helps identify hidden assets

- Expands understanding of website infrastructure

- Widely used in security assessments

- Assists in identifying publicly accessible services

## **Conclusion**

Domain and Subdomain Analysis is an important part of information gathering. It helps identify domain ownership details, DNS records, hosting information, historical website data, and publicly available subdomains. This information provides a better understanding of the target environment during the initial phase of security assessment.
