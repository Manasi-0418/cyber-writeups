# HTB Starting Point — Fawn & Dancing

## **Fawn Machine**

- **Connect to the Hack The Box VPN**.

	

- **Access the Fawn machine and review the provided tasks.**

- **Perform a network scan to identify open ports and services running on the target machine.**

nmap -sC -sV -O 10.129.60.227 -p- -Pn --min-rate=1000 -v

### **Command Explanation

nmap** -Nmap is a network scanning tool used to discover hosts, open ports, and running services on a target machine.

**-sC **- Runs Nmap's default scripts to gather additional information about the target services.

**-sV** - Detects the version of services running on open ports.

**-O** - Attempts to identify the operating system of the target machine.

**10.129.60.227 **- This is the target IP address that will be scanned.

**-p-**  -  Scans all 65535 TCP ports instead of only the most common ports.

**-Pn** - Skips host discovery and assumes the target is online.

**--min-rate=1000** - Sends packets at a minimum rate of 1000 packets per second to speed up the scan.

**-v** - Enables verbose mode and displays detailed scan progress.

**4.Analyze the scan results and identify the FTP service running on port 21.**

- Connect to the FTP service using an FTP client.

**7.Attempt anonymous login to the FTP server.**

Successfully access the FTP service using anonymous authentication.List the available files and directories on the server.

**8.Download the flag file to the local machine.

9.Read the contents of the file and obtain the flag.

10.Answer the HTB guided questions using the gathered information.

11.Submit the flag and successfully complete the Fawn machine.

Flag:**035db21c881520061c53e0536e44f815 

**Dancing Machine 

1.Connect to the Hack The Box VPN.

2.Access the Dancing machine and review the tasks provided by HTB.

3.Perform a network scan to identify open ports and running services.**

Command - nmap -sC -sV -O 10.129.60.227 -p- -Pn --min-rate=1000 -v

We enumerated SMB because Nmap identified port 445 running the SMB service. SMB enumeration helped discover shared folders and retrieve the flag from the accessible share.

**4.Enumerate available SMB shares on the target machine.**

Command - smbclient  -L //10.129.61.60// -N

### **Command Explanation -

smbclient**

- SMBClient is a command-line tool used to connect to and interact with SMB/CIFS network shares.

**-N**

- Attempts authentication with a null session (blank password).

- It tells SMBClient not to prompt for a password.

**-L**

- Lists all available SMB shares on the target system.

- It does not connect to a specific share; it only displays the available shares.

**//**<**target-ip**>**/**

- Specifies the target machine's IP address.

- SMBClient will query this system and display the available shares.

### **Purpose**

This command is used to discover SMB shares that are available on the target machine. It helps identify shared folders, administrative shares, and resources that may be accessible.

The SMB enumeration identified four available shares: ADMIN$, C$, IPC$, and WorkShares. ADMIN$, C$, and IPC$ were administrative shares, while WorkShares was an accessible disk share. Further enumeration was performed on the WorkShares share to identify available directories and files. 

**5.Identify the share that can be accessed without a password. Connect to the accessible SMB share.List the available directories and files.Navigate through the directories and locate the flag file.Download the file from the SMB share**.

**6.Read the contents of the file and obtain the flag.

7.Answer the HTB guided questions using the gathered information.

8.Submit the flag and successfully complete the Dancing machine.

Flag : -** 5f61c10dffbc77a704d76016a22f1664
