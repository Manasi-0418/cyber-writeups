# EH3 — Information Gathering and Footprinting

## **1. Information Gathering and Footprinting**

Information Gathering is the process of collecting information about a target before performing any security assessment or penetration testing. It helps security professionals understand the target environment and identify possible weaknesses.

The more information collected, the easier it becomes to understand the target system and plan security testing activities.

### **Why is Information Gathering Important?**

Before testing any system, it is necessary to know:

- Who is the target?

- What technologies are being used?

- Which systems are connected?

- What are the possible weak points?

Without proper information, testing becomes difficult and less effective.

### **Types of Targets**

- Person

- Network

- System

### **Example**

Suppose the target is a company website.

Before performing any assessment, information such as the following may be collected:

- Domain Name

- IP Address

- Technologies Used

- Email Addresses

- DNS Records

The process of collecting such information is known as Footprinting.

### **Common Methods Used -**

- Search Engine Research

- Social Media Analysis

- DNS Lookup

- Website Technology Detection

- Metadata Analysis

- Network Discovery

# **2. Types of Footprinting**

Footprinting can be classified into two types:

- Passive Footprinting

- Active Footprinting

## **i. Passive Footprinting**

Passive Footprinting is the process of collecting information about a target without directly interacting with its systems. In this method, information is gathered from publicly available sources.

The target is usually unaware that information is being collected.

### **Key Points**

- No direct interaction with the target system

- Does not generate logs on the target

- Generally safer and less risky

- Uses publicly available information

- Limited information may be obtained

### **Examples**

#### **1. Search Engine Research**

### **Search Engine Research**

Information about individuals or organizations can be collected using search engines. Publicly available information such as professional profiles, websites, images, business details, and social media accounts may appear in search results.

**Example:**
 Searching for a person's name on Google may reveal:

- Professional profiles

- Organization details

- Public images

- Contact information

- Related websites

#### **2. Social Media Analysis**

Social media platforms often contain useful information.

Examples:

- LinkedIn → Employee information

- Instagram → Photos and location details

- Facebook → Personal information

#### **3. WHOIS Lookup**

WHOIS provides domain registration details.

Example:

whois example.com

Information such as domain owner, registrar, and registration dates may be available.

#### **4. Job Portals**

Job advertisements can reveal technologies used by an organization.

Example:

If a company is hiring a React Developer, it may indicate that React technology is being used within the organization.

## **ii. Active Footprinting**

Active Footprinting is the process of collecting information by directly interacting with the target system or network.

Since communication occurs with the target, logs and traces may be generated.

### **Key Points**

- Direct interaction with target

- Generates logs and traces

- Provides more accurate information

- Can be detected by security devices

- Higher risk compared to passive footprinting

### **Examples**

#### **1. Ping Requests**

Used to determine whether a host is active on a network.

#### **2. Port Scanning**

Used to identify open ports and running services.

Example:

- Port 80 → HTTP

- Port 443 → HTTPS

- Port 22 → SSH

#### **3. Vulnerability Scanning**

Used to identify known security weaknesses in systems and applications.

#### **4. Banner Grabbing**

Used to identify software and service versions running on a target system.

# **Information Gathering of a Person (Footprinting)**

Information Gathering of a Person refers to the process of collecting publicly available information about an individual from online and offline sources. The purpose is to understand the person's identity, activities, interests, and professional background.

This information helps create a profile of the target and understand possible security risks.

## **Types of Information**

### **i. Personal Information**

Personal information includes basic details that identify a person.

Examples:

- Full Name

- Date of Birth

- Gender

- Nationality

- Language

- Photographs

This information helps establish the identity of an individual and connect information from different sources.

**Example:**

A LinkedIn profile may display a person's full name, photograph, and professional details.

### **ii. Contact Information**

Contact information refers to the methods used to communicate with a person.

Examples:

- Email Address

- Phone Number

- Residential Address

- Business Address

This information can be used to verify identity and establish communication.

**Example:**

A publicly available resume may contain an email address and contact number.

### **iii. Employment Information**

Employment information includes workplace details and job-related information.

Examples:

- Company Name

- Job Position

- Department

- Work Experience

This information helps understand the person's professional responsibilities.

**Example:**

LinkedIn Profile:
Cyber Security Analyst at ABC Technologies

### **iv. Social Media Profiles**

Social media profiles provide information about a person's activities, interests, and social connections.

Examples:

- LinkedIn

- Instagram

- Facebook

- X (Twitter)

Social media platforms often reveal personal and professional information.

**Example:**

An Instagram profile may show hobbies, travel activities, and daily routines.

### **v. Online Presence**

Online presence includes all publicly available information about a person on the internet.

Examples:

- Blogs

- Forums

- GitHub Accounts

- Portfolio Websites

This information helps identify interests, skills, and online activities.

**Example:**

A GitHub profile may contain programming projects and technical skills.

### **vi. Educational Background**

Educational background includes academic qualifications and institutions attended.

Examples:

- School Name

- College Name

- Degrees

- Certifications

This information helps understand a person's academic profile.

**Example:**

LinkedIn may show Bachelor's and Master's degree details.

### **vii. Family and Relationships**

This information includes details about family members, relatives, and close connections that are publicly shared.

Examples:

- Parents

- Siblings

- Friends

- Relatives

Such information may be available through social media platforms.

**Example:**

Family photographs shared on social networking sites.

### **viii. Legal and Public Records**

Public records contain information that may be legally available through government or public sources.

Examples:

- Property Records

- Business Registrations

- Court Records

These records help verify identity and ownership information.

### **ix. Financial Information**

Financial information relates to economic and business activities.

Examples:

- Business Ownership

- Public Company Information

- Financial Reports

This information is generally limited and may only be available through authorized public sources.

### **x. Interests and Hobbies**

Interests and hobbies reveal a person's preferences and activities.

Examples:

- Sports

- Music

- Gaming

- Photography

- Travelling

Understanding interests helps build a complete profile of an individual.

**Example:**

A social media bio may mention interests such as cricket, music, or fitness.

### **xi. Publicly Available Documents**

Documents available on public platforms may contain useful information.

Examples:

- Resume

- Research Papers

- Reports

- Presentations

These documents may contain contact information and professional details.

**Example:**

A resume uploaded online may include email address, phone number, and qualifications.

### **xii. Location and Travel Information**

Location information indicates places visited or current whereabouts that have been publicly shared.

Examples:

- Check-ins

- Travel Posts

- Event Participation

- Public Location Updates

This information helps understand movement patterns and travel history.

**Example:**

A social media post showing participation in a conference or trip.

### **Information Gathering of a System**

Types of Information

#### **i. Network Configuration**

Network configuration contains information related to system connectivity and communication within a network.

It includes:

- IP Address

- Subnet Mask

- Default Gateway

- DNS Server

**Example:**
 IP Address: 192.168.1.10

#### **ii. System Information**

System information provides details about the operating environment of a computer system.

It includes:

- Hostname

- Operating System

- System Architecture (32-bit / 64-bit)

- System Version

**Example:**
 Hostname: DESKTOP-01

Operating System: Windows 11

#### **iii. Hardware Information**

Hardware information describes the physical components installed in a system.

It includes:

- Processor (CPU)

- RAM

- Hard Disk

- Motherboard

**Example:**
 Processor: Intel Core i5

RAM: 8 GB

#### **iv. Running Services**

Running services are background processes that provide specific functions to the operating system and users.

Examples:

- Web Server

- Database Service

- Print Service

- Remote Access Service

#### **v. User Accounts**

User account information identifies the users who can access the system.

It includes:

- Usernames

- User Roles

- User Privileges

**Example:**
 Administrator Account

#### **vi. Installed Software and Applications**

Installed software information provides details about applications available on the system.

It includes:

- Software Name

- Version Information

- Installed Programs

- Security Software

**Example:**
 Google Chrome

Microsoft Office

Visual Studio Code

# **Information Gathering of a Network**

Information Gathering of a Network is the process of collecting information about network infrastructure, connected devices, services, and communication methods. It helps security professionals understand how a network operates and identify potential security risks.

The collected information provides a better understanding of the target network environment.

## **Types of Information**

### **i. IP Address and Subnets**

An IP Address is a unique identifier assigned to a device connected to a network. Subnets divide a network into smaller segments for better management and security.

Understanding IP addresses and subnet structures helps identify devices and network boundaries.

**Example:**

Website: example.com

IP Address: 192.168.1.1

### **ii. DNS System**

DNS (Domain Name System) converts domain names into IP addresses.

DNS records can reveal important information about servers and network infrastructure.

Examples:

- A Record

- MX Record

- NS Record

- TXT Record

**Example:**

mail.company.com

This may indicate the organization's mail server.

### **iii. Network Topology**

Network Topology refers to the arrangement and connection of devices within a network.

Common Types:

- Star Topology

- Bus Topology

- Ring Topology

- Mesh Topology

Understanding topology helps visualize communication paths and network structure.

**Example:**

A central server connected to multiple workstations in a star topology.

### **iv. Ports and Services**

Ports are communication endpoints used by network services.

Identifying open ports helps determine which services are running on a system.

Common Ports:

- Port 21 → FTP

- Port 22 → SSH

- Port 25 → SMTP

- Port 80 → HTTP

- Port 443 → HTTPS

**Example:**

An open Port 22 indicates that SSH service is available.

### **v. Operating Systems**

An Operating System (OS) manages hardware and software resources on a device.

Identifying the operating system helps understand the target environment.

Examples:

- Windows

- Linux

- macOS

**Example:**

A server running Linux Ubuntu.

### **vi. Network Security Devices**

Network security devices help protect systems and monitor network traffic.

Examples:

- Firewall

- IDS (Intrusion Detection System)

- IPS (Intrusion Prevention System)

- Proxy Server

These devices improve network security and help detect threats.

### **vii. Wireless Networks**

Wireless networks provide communication through Wi-Fi technology.

Important Information:

- SSID

- Encryption Type

- Access Points

- Signal Coverage

Common Security Standards:

- WPA2

- WPA3

**Example:**

Office Wi-Fi protected using WPA3 encryption.

### **viii. VPN Configuration**

A VPN (Virtual Private Network) provides secure communication over public networks.

VPNs help protect sensitive information by encrypting network traffic.

Examples:

- Remote Employee Access

- Secure Office Connectivity

### **ix. Network Protocols**

Protocols define rules for communication between devices.

Common Protocols:

- HTTP

- HTTPS

- FTP

- TCP

- UDP

- DNS

Understanding protocols helps identify network services and communication methods.

**Example:**

HTTPS encrypts communication between a user and a website.

### **x. Network Services and Applications**

Network services are applications running on servers and network devices.

Examples:

- Web Server

- Database Server

- Mail Server

- File Server

Identifying services helps understand the purpose of network resources.

### **xi. Remote Access Points**

Remote access allows users to connect to systems from outside the local network.

Examples:

- SSH

- RDP

- VPN Portal

These services are commonly used for system administration and remote work.

**Example:**

Port 3389 is commonly used by Remote Desktop Protocol (RDP).

### **xii. Network Traffic Analysis**

Network Traffic Analysis is the process of monitoring and studying data flowing through a network.

It helps understand communication patterns and identify unusual activities.

Common Tools:

- Wireshark

- Tcpdump

**Example:**

Analyzing network packets to understand communication between devices.

**Report of Website Technology Analysis Using Wappanalyzer

 **

1. Title

Website Technology Analysis Using Wappanalyzer

 

2. Objective

- To identify the technologies used by a website

- To understand frontend, backend, CMS, and server details

- To person passive information gathering

 

3. Introduction

- Wappalyzer is a tool used to detect technologies used in websites.

- It can identify:

i. CMS (WordPress, Joomla)

ii. Programming Language

iii. Frameworks

iv. Analytics tools

- It works as a browser extension or online tool

- It is part of passive footprinting, meaning no direct interaction with server.

4. Tools

- Google Chrome/ Firefox

- Wappalyzer Extension

- Internet Connection

 

5. Installation of Wappalyzer

Step 1:

- Open Google Chrome

- Go to Chrome Web Store

- Search for “Wappalyzer”

Step 3:

- Click on Add to Chrome

- Install the Extension

[i have already this extension, so if you don’t have then simply click that blue icon add button for download]

 

6. Performing Website Analysis

Step 1:

- Open any website

Ex.[ ](https://tryhackme.com)[https://tryhackme.com](https://tryhackme.com)

 

Step 2:

- Search for Wappalyzer

 

 

Step 3:

- Click on Add to Chrome

- Install Extension

 

7. Observed Technologies

i. CMS

ii. Programming Language

iii. Web Server

iv. JavaScript Libraries

v. Analytics Tools

vi. Security Tools

 

 

8. Result

- Successfully identified technologies used by the website

- Understood how websites are built using different tools

- Leaned passive footprinting technique

 

 

Adv.

i. Easy to use

ii. No Detection

iii. Provides quick results

 

Limitation

- May not show all techniques

- Some results may be incorrect

- Hidden technologies cannot be detected

 

 

 

**Website Technology Analysis using Whatweb in Linux**

 

1. Title

- Website Technology Analysis using WhatWeb Tool in kali linux

 

2. Objective

- To identify technologies used by website

- To perform information gathering using WhatWeb

- To understand passive footprinting in ethical hacking.

 

3. Introduction

- Whatweb is a kali linux tool used to detect technologies of websites.

- It Identifies: Same we were saw in windows chrome

4. Tools Required\

- Kali Linux

- Terminal Access

- Internet Connection

- WhatWeb

 

5. Checking WhatWeb Installation

Step i:

Open terminal and type:

- whatweb –version

 

6. Performing Website Analysis

Step 1: Basic Scan

- whatweb youtube.com

 

Step 2: Understanding Output

Whatweb will show:

- Web Server

- CMS

- Ip Address

- Country

- Technology

 

Step 3: Verbose Scan (more detailed)

- whatweb -v example.com

- -v = verbose ouput

 

9. Results

- Successfully identified website technologies using Whatweb

- Learned How to perform footprinting in kali linux

- Understood passive and aggressive scanning techniques.

 

Adv.

- Fast and simple tool

- Gives detailed information

- Works directly in kali linux

 

Limitation:

- Aggressive scan may be detected

- Some technologies may be hidden

- Requires internet connection.

 

Conclusion:

- WhatWeb is a powerful tool for information gathering

- Helps in identifying website technologies quickly

- Important for initial phase of ethical hacking
