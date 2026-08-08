# EH10 — Port Scanning, Service Scanning & OS Discovery

# **2. PORT SCANNING**

## **What is Port Scanning?**

Port Scanning is the process of examining network ports on a target system to determine their status and identify services running on those ports.

Since network services communicate through ports, identifying open ports helps determine which services are available and accessible on the target system.

### **Why Perform Port Scanning?**

Port scanning helps to:

- Identify open ports.

- Discover running services.

- Understand the functionality of a system.

- Detect unnecessary exposed services.

- Support vulnerability assessments and security audits.

### **Common Port States**

#### **Open**

A service is actively listening on the port and accepting incoming connections.

#### **Closed**

The port is accessible, but no application is currently listening on it.

#### **Filtered**

A firewall or security device is blocking access, preventing Nmap from determining whether the port is open or closed.

#### **Unfiltered**

The port is reachable, but Nmap cannot accurately determine whether it is open or closed.

| **Port ** | **Protocol** | ** Service** |
| --- | --- | --- |
| 21 | TCP | FTP (File Transfer Protocol) |
| 22 | TCP | SSH (Secure Shell) |
| 23 | TCP | Telnet |
| 25 | TCP | SMTP (Simple Mail Transfer Protocol) |
| 53 | TCP/UDP | DNS (Domain Name System) |
| 80 | TCP | HTTP (HyperText Transfer Protocol) |
| 443 | TCP | HTTPS (HyperText Transfer Protocol Secure) |
| 3306 | TCP | MySQL Database |
| 3389 | TCP | RDP (Remote Desktop Protocol) |

## **1. TCP Connect Scan**

### **Purpose**

Used to identify open TCP ports by establishing a complete TCP connection with the target.

### **Command

nmap** -**sT <**target-**ip**/24**>**

- **-**sT** → Perform TCP full Connect Scan.

- → Target system IP address.

- /24 - scan entire subnet Mask

### **How It Works**

Nmap performs a complete TCP three-way handshake with the target port.

- Nmap sends a SYN packet.

- The target responds with a SYN/ACK packet if the port is open.

- Nmap completes the connection by sending an ACK packet.

- The connection is then closed.

Because a full connection is established, this scan is easily logged and detected by the target system.

### **Observation**

Open TCP ports were successfully identified on active hosts within the 192.168.1.0/24 network. Nmap completed the full TCP three-way handshake with target ports and displayed the status of each discovered service. Because a complete connection was established, the scan activity can be logged and detected by the target system.

## **2. TCP SYN Scan**

### **Purpose**

Used to identify open ports without completing a full TCP connection. This method is commonly known as a Half-Open Scan or Stealth Scan.

### **Command

nmap** -**sS <**target-**ip**/24**>

 -**sS** → (Stealth Scan)TCP SYN Scan.

### **How It Works**

- Nmap sends a SYN packet to the target port.

- If the port is open, the target responds with a SYN/ACK packet.

- Instead of completing the connection, Nmap immediately sends a RST packet.

- The connection is terminated before the handshake is completed.

This method reduces connection logging and is faster than a TCP Connect Scan.

### **Observation**

Open ports were successfully identified using SYN packets. Since the connection was never fully established, the scan generated less network activity and provided a faster method of port discovery.

## **3. UDP Scan**

### **Purpose**

Used to identify open UDP ports on a target system.

### **Command - **nmap** -**sU <**target-**ip**>**

- **-**sU** → UDP Scan.

### **How It Works**

Nmap sends UDP packets to target ports and analyzes the responses.

- Open ports may respond with application-specific UDP data.

- Closed ports typically return an ICMP Port Unreachable message.

- No response may indicate that the port is open or filtered by a firewall.

Because UDP does not use a connection handshake, the scanning process is generally slower than TCP scanning.

### **Observation**

UDP services running on the target system were identified. The scan required additional time due to the connectionless nature of UDP communication and response-based analysis.

## **4. Fast Scan**

### **Purpose**

Used to quickly scan the most commonly used ports instead of performing a full port scan.

### **Command - **nmap** -F **<**target-**ip**>

-F** → Fast Scan (Top 100 common ports).

### **How It Works**

Nmap scans only its predefined list of frequently used ports rather than checking all available ports.

This significantly reduces scanning time while still identifying commonly exposed services.

### **Observation**

Commonly used ports were scanned quickly and efficiently. This method provided rapid visibility into frequently used services while reducing overall scan duration.

## **5. Full Port Scan**

### **Purpose**

Used to examine all TCP ports on a target system.

### **Command - **nmap** -p- **<**target-**ip**>**

- **-p-** → Scan all 65535 TCP ports.

### **How It Works**

Nmap checks every TCP port from 1 to 65535.

This approach provides a complete view of services running on the target system, including services operating on uncommon or non-standard ports.

Because every port is examined, the scan requires more time than Fast Scan or default scanning methods.

### **Observation**

All TCP ports were successfully examined, allowing both common and uncommon services to be identified. The scan provided a comprehensive overview of the target's exposed services and network accessibility.

# **4. SERVICE Scanning**

## **What is Service Scanning?**

Service Discovery is the process of identifying services running on open ports and determining their version information. After discovering open ports, the next step is to identify the applications and services associated with those ports.

Common examples of network services include:

- HTTP

- HTTPS

- FTP

- SSH

- SMB

- DNS

Understanding these services helps security professionals gain deeper insight into the target environment.

## **Why Perform Service Discovery?**

Service discovery helps to:

- Identify running services.

- Determine software versions.

- Understand target functionality.

- Support vulnerability assessment.

- Improve enumeration accuracy.

## **1. Service Version Detection**

### **Purpose**

Used to identify services and their version information running on open ports.

### **Command - **nmap** -**sV <**target-**ip**>**

- **nmap** → Network scanning tool.

- **-**sV** → Service Version Detection.

- → Target system IP address.

### **How It Works**

Nmap sends specially crafted probe packets to open ports and analyzes the responses returned by the target service.

The responses are compared against Nmap's internal **nmap**-service-probes** database, which contains thousands of known service signatures.

Using this probe matching process, Nmap can identify both the service name and its software version.

### **Observation**

Running services and their version information were successfully identified on the target system. The collected version details can assist in further enumeration and vulnerability assessment activities.

## **2. Default Script Scan**

### **Purpose**

Used to gather additional information about services using Nmap's built-in scripting engine.

### **Command - **nmap** -**sC <**target-**ip**>**

- **-**sC** → Runs the default Nmap Scripting Engine (NSE) scripts.

### **How It Works**

Nmap includes a scripting framework known as the **Nmap Scripting Engine (NSE)**.

When the **-**sC** option is used, Nmap executes a predefined set of safe scripts against the target services.

These scripts collect additional information such as:

- Service configuration details

- Authentication methods

- SSL certificate information

- SMB information

- HTTP headers

The default scripts are designed to gather information without causing disruption to the target system.

### **Observation**

Additional service and configuration details were successfully collected using default NSE scripts. The scan provided valuable information that can support further analysis and security assessment.

## **3. Service Version Detection and Default Script Scan**

### **Purpose**

Used to perform service version detection and default script scanning simultaneously.

### **Command - **nmap** -**sV** -**sC <**target-**ip**>**

- **-**sV** → Service Version Detection.

- **-**sC** → Default NSE Scripts.

### **How It Works**

Nmap first identifies services and software versions running on open ports.

After service identification, it automatically executes default NSE scripts against the discovered services.

This combined approach gathers detailed service information and configuration data within a single scan.

### **Observation**

Detailed information about running services, software versions, and service configurations was successfully gathered in a single scan. Combining service detection and script scanning improved the efficiency of information gathering.

## **4. Aggressive Scan**

### **Purpose**

Used to gather comprehensive information about a target system using multiple scanning techniques simultaneously.

### **Command - **nmap** -A **<**target-**ip**>**

- **-A** → Aggressive Scan.

### **Components Included in Aggressive Scan**

| **Component** | **Flag** | **Purpose** |
| --- | --- | --- |
| OS Detection | -O | Identifies operating system |
| Service Detection | -sV | Identifies service versions |
| Script Scanning | -sC | Executes default NSE scripts |
| Traceroute | --traceroute | Maps the network path |

### **How It Works**

The Aggressive Scan combines several advanced Nmap features into a single command.

It performs:

- Operating System Detection

- Service Version Detection

- Default Script Scanning

- Traceroute Analysis

This provides a detailed overview of the target system and its network environment.

Because multiple techniques are used simultaneously, the scan generates more network traffic than standard scans.

### **Observation**

The aggressive scan successfully gathered extensive information about the target system, including operating system details, service versions, script results, and network path information.

# **5. OS DISCOVERY**

## **What is OS Discovery?**

OS Discovery (Operating System Discovery) is the process of identifying the operating system running on a target machine.

Banner grabbing or OS fingerprinting is a method used to determine the operating system that is running on a remote target system.

**Types of OS Discovery

1. Active Banner Grabbing**

In active banner grabbing, specially crafted packets are sent to the remote operating system and the responses are analyzed. These responses are then compared with a database of known OS signatures to determine the target operating system.

Examples:

- Nmap OS Detection

- Xprobe2

 

**2. Passive Banner Grabbing**

Passive banner grabbing depends on the different implementations of the TCP/IP stack and the way operating systems respond to network packets. It does not require direct interaction with the target system.

Passive banner grabbing includes:

- Banner grabbing from error messages 

- Network traffic sniffing 

- Banner grabbing from page extensions and headers

The operating system is identified based on characteristics such as:

- TTL values

- TCP Window Size

- TCP Options

- Packet behavior

Examples:

- Wireshark

- p0f

| **Operating System** | **Default TTL** | **TCP Window Size** |
| --- | --- | --- |
| Linux | 64 | 5840 |
| FreeBSD | 64 | 65535 |
| OpenBSD | 255 | 16384 |
| Windows | 128 | 65535 to 1 MB |
| Cisco Router | 255 | 4128 |
| Solaris | 255 | 8760 |
| IBM AIX | 255 | 16384 |

## **Why Perform OS Discovery?**

OS Discovery helps to:

- Identify the operating system.

- Understand the target environment.

- Improve enumeration accuracy.

- Support vulnerability assessment.

- Select appropriate security testing techniques.

## **OS Detection Scan**

### **Purpose**

Used to identify the operating system running on a target host.

## **How It Works**

Nmap sends specially crafted TCP, UDP, and ICMP packets to the target host.

The responses are analyzed based on characteristics such as:

- TTL (Time To Live)

- TCP Window Size

- TCP Flags

- TCP Sequence Numbers

- ICMP Response Behavior

The collected information is compared against Nmap's fingerprint database (**nmap-os-db**).

The closest matching fingerprint is returned as the detected operating system.

This process is known as **OS Fingerprinting**.

### **Command - **nmap** -O **<**target-**ip**>**

- **nmap** → Network scanning tool.

- **-O** → Operating System Detection.

- → Target system IP address.

**ping 192.168.1.43

sudo** hping3 -8 0-100 -S 192.168.1.4**3**

This error indicates that the hping3 application encountered a buffer overflow condition and crashed before completing the scan. The issue is related to the tool or its execution environment rather than the target host. As a result, the TCP Window Size could not be determined using hping3. Alternative tools such as Nmap OS Detection (nmap -O) were considered for further analysis**.**

The scan could not be completed due to an internal hping3 buffer overflow error, resulting in abnormal termination of the process**.**

## **Observation**

The operating system running on the target host was successfully identified using OS fingerprinting techniques. Network response characteristics such as TTL values, TCP window size, and packet behavior were analyzed and compared against known operating system fingerprints to determine the most likely operating system.
