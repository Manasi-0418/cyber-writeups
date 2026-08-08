# EH8 — Information Gathering (Dmitry, Wget, Curl, Domain Dossier, Sherlock, SIGIT)

** IP Tracker, Sherlock and SIGIT**

# **1. Dmitry Scan Report**

### **What is Dmitry?**

Dmitry (Deepmagic Information Gathering Tool) is a Linux-based command-line tool used to collect information about a target website.

It helps gather:

- WHOIS information

- Subdomains

- Email addresses

- Open ports

- Netcraft information

### **Command**

dmitry -iwnse whitebandassociates.com

### **Parameters**

- i → WHOIS information

- w → WHOIS lookup

- n → Netcraft information

- s → Subdomain search

- e → Email address search

### **Observation**

The Dmitry tool successfully collected information related to the target domain, including WHOIS records, subdomains, email addresses, and network information.

## **2. Wget Tool**

### **What is Wget?**

Wget is a command-line utility used to download files and website content from the internet.

It supports:

- HTTP

- HTTPS

- FTP

Wget is commonly used to download web pages and website resources directly from the terminal.

### **Command**

wget -mv[ ](https://whitebandassociates.com/)[https://whitebandassociates.com/](https://whitebandassociates.com/)

### **Parameters**

- m → Mirror Website

- v → Verbose Output

### **Information Observed**

#### **i. DNS Resolution**

The domain was resolved into multiple IP addresses.

#### **ii. Connection**

A secure connection was established using HTTPS on port 443.

#### **iii. Redirect**

The website redirected to another URL.

#### **iv. Cookie Information**

The output showed cookies associated with the website.

#### **v. Response Status**

HTTP 200 OK indicated that the webpage loaded successfully.

#### **vi. File Download**

The webpage was saved as:

index.html

### **Observation**

The wget command displayed DNS information, connection details, redirects, response codes, and successfully downloaded website content.

## **3. Curl Tool**

### **What is Curl?**

Curl is a command-line tool used to transfer data from servers and retrieve webpage content.

It is commonly used to view website source code directly from the terminal.

### **Command**

curl -L[ ](https://whitebandassociates.com/)[https://whitebandassociates.com](https://whitebandassociates.com/)

### **Parameter**

- L → Follow Redirects

### **Output**

The command displayed the HTML source code of the target website.

### **Uses**

- View webpage source code

- Identify technologies

- Check scripts

- Perform basic reconnaissance

### **Observation**

The curl command retrieved the HTML source code and displayed website content directly in the terminal.

## **4. Domain Dossier**

### **What is Domain Dossier?**

Domain Dossier is an online information gathering tool used to collect information related to domains and IP addresses.

### **Purpose**

It helps perform:

- Domain Analysis

- DNS Investigation

- IP Analysis

- Subdomain Discovery

- WHOIS Lookup

### **Benefits**

- Easy to use

- Provides multiple domain details

- Useful during reconnaissance

- Supports passive information gathering

### **Observation**

Domain Dossier provided DNS records, WHOIS information, IP details, and domain-related information associated with the target website.

## **5. IP-Tracker.org**

### **What is IP-Tracker?**

IP-Tracker.org is an online tool used to gather publicly available information related to IP addresses and domains.

### **Information Available**

- IP Address Information

- ISP Details

- DNS Information

- SSL Certificate Information

- Hosting Details

- Location Information

### **Applications**

- Networking

- Information Gathering

- Reconnaissance

- Infrastructure Analysis

### **Observation**

IP-Tracker displayed publicly available information related to the target IP address, including ISP details, DNS records, hosting information, and server details.

## **6. IP-Tracer=github**

### **What is IP-Tracer?**

IP-Tracer is an open-source tool used to obtain information related to an IP address.

It works on:

- Kali Linux

- Termux

### **Information Obtained**

- Country

- City

- ISP

- Latitude

- Longitude

Step for download tracer

i. git clone[ ](https://github.com/rajkumardusad/IP-Tracer.git)[https://github.com/rajkumardusad/IP-Tracer.git](https://github.com/rajkumardusad/IP-Tracer.git)

ii. cd IP-Tracer

iii. chmod +x *

iv. ./install

v. ip-tracer -m

### **Purpose**

IP-Tracer helps identify publicly available geographical and network-related information associated with an IP address.

### **Observation**

The tool successfully displayed location information and network details related to the target IP address.

## **7. Sherlock (Username Finder Tool)**

### **What is Sherlock?**

Sherlock is an open-source OSINT tool used to search for usernames across multiple social media platforms and websites.

### **Purpose**

- Track online presence

- Find social media accounts

- Support OSINT investigations

- Identify digital footprints

### **Working**

The tool checks whether a specific username exists across different online platforms.

### **Observation**

Sherlock identified platforms where the specified username was publicly available and helped analyze the target's online presence.

## **8. SIGIT (Social Information Gathering Intelligence Tool)**

### **What is SIGIT?**

SIGIT is an open-source OSINT tool used to collect information from multiple public sources.

### **Purpose**

Gather information related to:

- Domains

- IP Addresses

- Emails

- Usernames

### **Features**

- User Reconnaissance

- Phone Information

- Email Analysis

- IP Lookup

- DNS Reconnaissance

- WHOIS Lookup

- SSL Analysis

### i. Installation

### - git clone[ ](https://github.com/termuxhackz/sigit.git)[https://github.com/termuxhackz/sigit.git](https://github.com/termuxhackz/sigit.git)

### - cd sigit

### - python3 install.py

###  ii. Usage

### - python3 sigit.py

The user can select different options based on the type of information required.

### **Observation**

SIGIT combined multiple reconnaissance techniques and provided information related to domains, usernames, IP addresses, and other publicly available resources.
