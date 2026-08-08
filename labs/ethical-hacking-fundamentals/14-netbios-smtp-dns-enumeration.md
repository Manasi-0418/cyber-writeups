# EH14 — Enumeration: NetBIOS, SMTP, DNS

NetBIOS (Network Basic Input/Output System) is a networking protocol used for communication between computers on a local network. It is commonly used in Windows systems for file sharing, printer sharing, and resource identification.

NetBIOS Enumeration is the process of collecting information such as:

- Host names

- Workgroup or domain names

- Shared resources

- User information

- Network services

### **Commands Used**

#### **Windows**

- nbtstat -A <IP Address> Displays NetBIOS name table of the remote host.

- nbtstat -c Displays NetBIOS name cache.

- nbtstat -r Displays NetBIOS name resolution statistics.

#### **Linux **

- nmap -sC sV -p 139 --script nbstat.nse <IP Address> -v

Enumerates NetBIOS information such as hostname and workgroup.

### **Observation**

- NetBIOS service was detected on port 139.

- Hostname information was obtained.

- Workgroup/domain information was identified.

- Network resources were successfully enumerated.

NetBIOS Enumeration was successfully performed and information about the target host and workgroup was obtained.

# **2. SMTP Enumeration**

SMTP (Simple Mail Transfer Protocol) is used for sending email messages between servers.

SMTP Enumeration helps identify:

- Valid usernames

- Mail server information

- SMTP service details

### **Commands Used**

- nmap -sV -p 25 --script smtp* <IP Address> -v

Enumerates SMTP service information.

- nc -nv <IP Address> 25

Connects to SMTP service using Netcat.

VRFY root

VRFY admin

Checks whether a username exists on the mail server.

### **Observation**

- Port 25 was identified and SMTP service filtering was observed .

- SMTP banner information was obtained.

- User verification attempts were performed.

- Mail service details were identified.

SMTP Enumeration was successfully performed and mail service information was gathered.

# **3. DNS Enumeration**

DNS (Domain Name System) translates domain names into IP addresses and stores different types of DNS records.

DNS Enumeration is performed to collect information about:

- IPv4 addresses

- IPv6 addresses

- Mail servers

- Name servers

- Domain authority records

## **Commands Used -

i.Domain Record**

- host [whitebandassociates.com](http://whitebandassociates.com)

### **ii.**A Record**

- host -t A [whitebandassociates.com](http://whitebandassociates.com)

Returns IPv4 address of the domain.

### **iii.**AAAA Record**

- host -t AAAA [whitebandassociates.com](http://whitebandassociates.com)

Returns IPv6 address of the domain.

### **iv.**MX Record**

- host -t mx [whitebandassociates.com](http://whitebandassociates.com)

Displays Mail Exchange servers.

### **v.**NS Record**

- host -t ns [whitebandassociates.com](http://whitebandassociates.com)

Displays Name Servers.

### **vi.**SOA Record**

- host -t SOA [whitebandassociates.com](http://whitebandassociates.com)

Displays Start of Authority information.

### **vii.**CNAME Record**

- host -t CNAME [whitebandassociates.com](http://whitebandassociates.com)

Displays Canonical Name record.

**viii.TXT Record**

- host -t TXT <domain name>

### **ix.**Using NSLOOKUP**

- nslookup

- set type=ns

- whitebandassociates.com

Displays Name Server information.

- set type=mx

- whitebandassociates.com

Displays Mail Server information.

### **x.**Using DIG**

- dig [google.com](http://google.com)

Displays detailed DNS information.

- dig whitebandassociates.com -t mx

Displays MX records.

### **xi.**Using DNSRecon**

- dnsrecon -d [google.com](http://google.com)

Collects DNS records such as:

- IPv4

- IPv6

- NS

- MX

- SOA

- SRV

## **Observation**

- DNS records were successfully queried.

- A, AAAA, MX, NS and SOA records were identified.

- Mail server and Name Server information was obtained.

- Domain information was successfully enumerated.

DNS Enumeration was successfully performed and important DNS records of the target domain were obtained.

**Tool -enum4linux**

- enum4linux -A <IP Address>

**Purpose:**

- Enumerates users

- Enumerates shares

- Enumerates workgroup/domain information

- Collects NetBIOS and SMB information
