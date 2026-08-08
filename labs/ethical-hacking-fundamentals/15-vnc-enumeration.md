# EH15 — Enumeration: VNC

**Step 1 - Scan the network to identify active hosts and open services.**

Command: nmap -sV 192.168.1.0/24

Observation:
 Nmap was used to scan the network and identify active hosts and running services. Multiple open ports were detected on the target machine.

### **Step 2 - **Identify the VNC service running on the target host.**

Observation:

The scan results showed that TCP Port 5900 was open on 192.168.1.36, indicating the presence of a VNC service .

**Step 3:-Launch the Metasploit Framework.**

Command:- msfconsole

**Step 3:-**

Observation:Metasploit Framework was started to perform additional VNC enumeration. 

### **Step 4 **- **Search for VNC-related modules in Metasploit.**

Command : search vnc

**Observation: Available VNC-related auxiliary modules were listed for further enumeration and analysis.

### **Step 5 - **Review the selected VNC auxiliary module.

Command: info auxiliary/scanner/vnc/vnc_root_pw

Observation: The module information, options, and description were reviewed to understand its purpose and configuration requirements.

### **Step 6 - **Verify VNC connectivity using a VNC client.**

Command: vncviewer 192.168.1.36

Observation: The VNC client connected to the target host and requested authentication, confirming that the VNC service was active and reachable. 

### **Step 7 - **Access and verify the remote desktop environment.**

Observation: The remote desktop session was successfully displayed, confirming that the VNC service was functioning properly and allowing remote graphical access to the target system. 

### **Step 8: Directory Verification**

Observation:

The file system was examined using Linux commands. The previously created **"**cyber**"** directory was successfully located and verified on the target system, confirming that the directory creation operation had been completed successfully.

The created **"**cyber**"** directory was successfully verified on the target machine
