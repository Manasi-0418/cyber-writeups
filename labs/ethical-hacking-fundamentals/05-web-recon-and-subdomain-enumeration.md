# EH5 — Web Application Reconnaissance & Subdomain Enumeration

## **1. Subdomain Enumeration**

### **Introduction**

Subdomain Enumeration is the process of identifying subdomains associated with a target domain. Subdomains are subdivisions of a main domain and are often used to host different services such as web applications, email services, APIs, and administrative portals.

Discovering subdomains helps security professionals understand the structure of a website and identify additional publicly accessible assets.

C99 shell is a web-based hacking tool (web shell) used after a website is already.

It allows:

- File access

- Command execution

- Server control

So it is used in Post-exploitation phase, not reconnaissance

### **Example**

Main Domain:

google.com

Subdomains:

- mail.google.com

- drive.google.com

- maps.google.com

### **Why Do We Perform Subdomain Enumeration?**

- To identify hidden services

- To discover additional assets

- To understand website infrastructure

- To identify publicly accessible resources

- To improve visibility of the target environment

### **Observation**

Subdomain enumeration helps identify services associated with a target domain and provides a broader understanding of the web infrastructure.

## **2. VirusTotal (Reconnaissance Tool)**

### **Introduction**

VirusTotal is a free online platform used to analyze files, URLs, domains, and IP addresses. It combines information from multiple antivirus engines and open-source intelligence (OSINT) sources.

VirusTotal can provide valuable information about domains and infrastructure during the information gathering phase.

### **Uses of VirusTotal**

- Domain Analysis

- URL Analysis

- IP Address Information

- DNS Records

- Security Reputation

- Infrastructure Analysis

### **Why Use VirusTotal in Reconnaissance?**

- Identify subdomains

- View DNS records

- Check IP addresses

- Analyze domain reputation

- Discover related infrastructure

### **Observation**

VirusTotal provided information related to the target domain, including DNS records, IP addresses, domain reputation, and associated infrastructure.

## **3. Subdomain Relations**

### **What are Subdomain Relations?**

Subdomain Relations describe how subdomains are connected to the main domain through DNS records, hosting infrastructure, and services.

### **Example**

Main Domain:

google.com

Related Subdomains:

- mail.google.com → Email Service

- drive.google.com → Cloud Storage

- maps.google.com → Mapping Service

These services belong to the same organization and share infrastructure resources.

### **Importance**

- Helps understand service relationships

- Identifies connected assets

- Improves visibility of website architecture

### **Observation**

Subdomain relation analysis revealed connections between different services operating under the same domain.

eh

## **4. VirusTotal Details Section**

### **Introduction**

The Details section of VirusTotal provides technical information related to a domain.

### **Information Available**

- Domain Owner Information

- Registration Details

- Hosting Information

- Domain Reputation

- Analysis History

### **Benefits**

- Better understanding of the domain

- Infrastructure visibility

- Reputation analysis

- Security assessment support

### **Observation**

The Details section displayed metadata and technical information associated with the target domain.

## **5. SSL Certificate Transparency Logs**

### **Introduction**

Certificate Transparency Logs contain publicly available records of SSL/TLS certificates issued for websites.

These records may reveal additional subdomains associated with a domain.

### **Information Found in Certificates**

- Common Name (CN)

- Subject Alternative Name (SAN)

### **Example Subdomains**

- login.example.com

- api.example.com

- test.example.com

### **Benefits**

- Passive information gathering

- Discovery of hidden subdomains

- Certificate history analysis

### **Observation**

Certificate Transparency Logs revealed domain-related certificate information and associated subdomains useful for passive reconnaissance.

## **6. DNS Records and Historical Information**

VirusTotal stores and indexes information related to:

- DNS Records

- MX Records

- CNAME Records

- Passive DNS History

- Historical Domain Information

This information helps security professionals understand changes in infrastructure over time.

### **Observation**

Historical DNS information provided insights into domain configuration and infrastructure changes.

## **7. Red Hawk**

### **Introduction**

Red Hawk is an information gathering and reconnaissance tool available on GitHub. It collects publicly available information related to domains and websites.

### **Objectives**

- Gather domain information

- Identify subdomains

- Collect server details

- Analyze DNS information

### **Features**

- Subdomain Discovery

- IP Address Identification

- DNS Information

- Server Information

- Basic Security Checks

### **Procedure**

- Open Kali Linux.

- Obtain the tool from GitHub.

- Navigate to the tool directory.

- Run the tool.

- Enter the target domain.

### **Working**

Red Hawk collects publicly available information related to:

- Subdomains

- IP Addresses

- DNS Records

- Server Information

### **Advantages**

- Easy to use

- Fast scanning

- Beginner friendly

- Simple interface

### **Limitations**

- Provides basic information only

- Not suitable for advanced assessments

- Results may vary

### **Observation**

Red Hawk successfully collected publicly available information related to the target domain and infrastructure.

## **8. crt.sh (Subdomain Enumeration Tool)**

### **Introduction**

crt.sh is a web-based tool used for subdomain enumeration through Certificate Transparency Logs.

### **Objectives**

- Discover subdomains

- Analyze SSL/TLS certificates

- Perform passive reconnaissance

### **Features**

- No installation required

- Fast and easy to use

- Historical certificate data

- Certificate Transparency analysis

### **Procedure**

- Open a web browser.

- Visit the crt.sh website.

- Enter the target domain.

- Click Search.

- Review the discovered subdomains.

### **Advantages**

- Passive reconnaissance

- No direct interaction with target systems

- Large amount of publicly available data

- Free to use

### **Limitations**

- Only shows certificate-related domains

- May contain duplicate entries

- Some results may be outdated

### **Observation**

crt.sh identified multiple subdomains associated with SSL/TLS certificates issued for the target domain.
