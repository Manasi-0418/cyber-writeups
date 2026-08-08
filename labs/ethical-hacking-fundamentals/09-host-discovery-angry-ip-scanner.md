# EH9 — Scanning: Host Discovery with Angry IP Scanner

**------------------------------------------------**

## SCANNING NETWORKS

### **Introduction**

Scanning is the process of gathering detailed information about a target network or system. It is performed after the reconnaissance phase and before vulnerability assessment or penetration testing.

The purpose of scanning is to identify active hosts, open ports, running services, operating systems, and potential security weaknesses within a network.

Unlike reconnaissance, which mainly collects publicly available information, scanning directly interacts with target systems to obtain technical information.

### **Why Scanning is Important**

Scanning helps security professionals:

- Identify active systems in a network.

- Discover open ports and running services.

- Determine the operating system of target hosts.

- Perform banner grabbing and service enumeration.

- Identify vulnerabilities and security weaknesses.

- Create a profile of the target environment.

### **Objectives of Scanning**

- Check live systems and open ports.

- Identify services running on active hosts.

- Perform banner grabbing and OS fingerprinting.

- Detect network vulnerabilities.

- Gather information for security assessment.

### **Types of Scanning**

1. Host Discovery
 Used to identify active devices in a network.

2. Port Scanning
 Used to identify open ports on a target system.

3. Service Discovery
 Used to identify services and their versions.

4. OS Discovery
 Used to determine the operating system running on a target host.

5. Firewall / IDS Evasion
 Used to understand how scanning interacts with security controls.

6. Vulnerability Scanning
 Used to identify known vulnerabilities in services and systems.

## **1. HOST DISCOVERY**

### **What is Host Discovery?**

Host Discovery is the process of identifying active devices in a network before performing detailed scans. It helps determine which hosts are alive and responding to network requests.

### **Why Host Discovery?**

Without host discovery, Nmap would waste time scanning systems that are offline.

**Benefits:**

- Reduces scan time.

- Identifies active hosts.

- Improves scanning efficiency.

- Helps map the network.

### Host Discovery Techniques

#### **1. ARP Ping Scan 

ARP (Address Resolution Protocol)** is used to map an IP address to a MAC address within a local network, enabling devices to communicate with each other on the same subnet. 

**Purpose -**
 Used to discover active hosts within a local subnet using ARP requests.

**Command** - **nmap -sn -PR 192.168.1.0/24**

- nmap → Network scanning tool.

- -sn → Host discovery only (disable port scanning).

- -PR → Perform ARP Ping Scan.

- 192.168.1.0/24 → Scan the entire subnet.

**How It Works -**
 Nmap sends ARP requests to IP addresses within the target subnet. 
 If a device replies with an ARP response, Nmap marks it as alive.
 ARP scanning is very fast and reliable within a LAN environment.
 ARP scanning only works within the same subnet. It cannot cross routers or work across different networks.

**Observation -**
 Active hosts in the local subnet were successfully identified using ARP requests and responses.

ARP scanning proved to be a fast and reliable host discovery technique within the local network because devices must respond to ARP requests to communicate on the LAN. 

#### **2. UDP Ping Scan**

ICMP → Used for network diagnostics and status messages.

UDP → Used for fast data transmission without connection setup.

**Purpose - **
Used to identify live hosts using UDP packets, especially when ICMP is blocked.

**Command - **nmap -sn -PU 192.168.1.0/24**

- -PU → UDP Ping Scan.

**How It Works -**
 Nmap sends UDP packets to the target host.
 If the port is closed, the target responds with an ICMP Port Unreachable message — this confirms the host is alive.
 If no response is received, the host may be offline or a firewall is dropping the packets.
 This technique is useful when ICMP Echo Requests are blocked by a firewall.

**Observation**
Live hosts were successfully identified using UDP-based host discovery.UDP Ping Scan can help detect active systems when traditional ICMP Echo Requests are filtered or restricted.

#### **3. ICMP Echo Ping Scan

Purpose -**
 Used to determine whether a host is reachable using ICMP Echo Requests.

**Command - **nmap -sn -PE 192.168.1.0/24**

- -PE → ICMP Echo Ping Scan.

**How It Works -**
 Nmap sends ICMP Echo Requests to the target.
 If the host replies with an ICMP Echo Reply, the host is considered alive.
 This is the most common and traditional method of checking host availability, similar to the standard ping command.

**Observation**
 Hosts responding to ICMP Echo Requests were identified as active. However, many firewalls block ICMP Echo Requests, making this method unreliable in hardened environments.

#### **4. ICMP Timestamp Ping Scan

Purpose -**
Used to discover active hosts by sending ICMP Timestamp Requests and analyzing Timestamp Replies from target systems.

**Command - **nmap -sn -PP 192.168.1.0/24**

- -PP → ICMP Timestamp Ping Scan.

**How It Works**
 Nmap sends ICMP Timestamp Requests to the target.
 If the host responds with an ICMP Timestamp Reply, it is considered active.
 Some firewalls block ICMP Echo Requests but allow Timestamp Requests, making this a useful alternative.

**Observation**
 Active hosts responded to ICMP Timestamp Requests. This method is useful when standard ICMP Echo scans are blocked but Timestamp Requests are still permitted through the firewall.

#### **5. ICMP Address Mask Ping Scan

Purpose -**
Used to identify active hosts by sending ICMP Address Mask Requests and detecting systems that respond with Address Mask Replies.

**Command -** nmap -sn -PM 192.168.1.0/24**

- -PM → ICMP Address Mask Ping Scan.

**How It Works -**
 Nmap sends ICMP Address Mask Requests to the target.
 If the host responds with an ICMP Address Mask Reply, it is considered active.
 This is a lesser-known ICMP type that may pass through firewalls that block standard Echo Requests.

**Observation -**
 Host availability was verified using Address Mask Requests. This technique is effective in environments where both Echo and Timestamp ICMP types are filtered.

#### **6. TCP SYN Ping Scan

Purpose -**
 Used to identify live hosts using TCP SYN packets.

**Command - **nmap -sn -PS 192.168.1.0/24**

- -PS → TCP SYN Ping Scan.

**How It Works - **
 Nmap sends TCP SYN packets to the target host.
 If the host is active and the port is open, it responds with a SYN/ACK packet.
 If the port is closed, the host responds with a RST packet.
 Both SYN/ACK and RST responses confirm the host is alive.
 Nmap does not complete the three-way handshake — it sends a RST after receiving the response.

**Observation -**
 Live hosts were discovered through TCP SYN probing. This method is effective when ICMP is blocked, as it uses TCP traffic which is commonly allowed through firewalls.

#### **7. TCP ACK Ping Scan

Purpose** - Used to identify active hosts using TCP ACK packets.

**Command **-** nmap -sn -PA 192.168.1.0/24**

- -PA → TCP ACK Ping Scan.

**How It Works -**
 Nmap sends TCP ACK packets to the target host.
 Since there is no prior connection established, the target responds with a RST (Reset) packet.
 This RST response confirms that the host is alive, even though no actual connection is formed.
 This technique is useful for bypassing firewalls that block incoming SYN packets but allow ACK packets through.

**Observation - **
Active hosts were successfully identified through TCP ACK probes.Hosts responded with RST packets, indicating that the systems were active and reachable.

#### **8. IP Protocol Ping Scan

Purpose -**
 Used to identify active hosts by sending packets using different IP protocols.

**Command - **nmap -sn -PO 192.168.1.0/24**

- -PO → IP Protocol Ping Scan.

**How It Works -**
 Nmap sends packets using multiple IP protocols such as ICMP, IGMP, and IP-in-IP.
 If the host is active, it responds to at least one of these protocol packets.
 Any valid response from the target confirms the host is alive.
 This method increases the chance of detection when specific protocols are filtered.

**Observation -**
Live hosts were detected through IP protocol probing.(An IP Protocol Probe is a packet sent using a specific IP protocol number to determine whether a target host is active and responds to that protocol. )

By using different IP protocol types, the scan increased the likelihood of receiving a valid response from active systems and helped identify hosts that may not respond to traditional ping methods.

**HOST DISCOVERY USING ANGRY IP SCANNER **

### **What is Angry IP Scanner?**

Angry IP Scanner is a fast and lightweight network scanning tool used to discover active hosts within a network. It scans a specified range of IP addresses and displays information about the devices that respond during the scan.

The tool can provide details such as:

- IP Address

- Hostname

- Ping Status

- MAC Address

- Open Ports

It is available for Windows, Linux, and macOS operating systems.

### **Why Use Angry IP Scanner?**

- Simple and user-friendly graphical interface.

- Performs fast network scanning.

- Quickly identifies active devices on a network.

- Displays useful network information in an organized format.

- Useful for network administration and security assessments.

### **Installation**

#### **Step 1**

Download Angry IP Scanner from its official website.

#### **Step 2**

Install the application by following the setup instructions.

#### **Step 3**

Launch the application after installation.

### **Configuration**

#### **Step 1**

Enter the IP address range to be scanned.

Example:

192.168.1.0 – 192.168.1.255

#### **Step 2**

Select the required scanning options and information fields.

#### **Step 3**

Click the **Start** button to begin scanning.

### **How It Works**

Angry IP Scanner sends ping requests to each IP address within the selected range.

If a device responds, it is marked as active and displayed in the results.

Depending on the scan configuration, the tool may also collect additional information such as hostname, MAC address, and open ports.

The scan results help administrators and security professionals identify devices currently connected to the network.

### **Observation**

The scan successfully identified active hosts within the specified IP range. Information such as IP addresses, hostnames, MAC addresses, and network status was displayed for the discovered devices. Angry IP Scanner provided a quick and efficient method for identifying systems available on the network.
