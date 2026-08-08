# EH16 — Enumeration: NFS

To Enumerate the NFS (network file system) service running on metasploitable and access the shared directory from kali linux.

## **Introduction** - **NFS (Network File System) is a distributed file-sharing protocol that enables Linux and Unix systems to share directories over a network. It allows users on one machine to access files and folders stored on another machine as if they were available locally.

## **Step 1: Identify the Target IP Address**

### **Command**

ifconfig

### **Purpose**

To display network interface details and determine the IP address of the Metasploitable machine, which will be used as the target during enumeration.

## **Step 2: Perform Initial Enumeration**

### **Command**

nmap -sCV 192.168.1.46

### **Purpose**

- Discover open ports on the target host.

- Identify running services.

- Gather service and version information.

### **Observation**

The scan detected multiple active services on the target machine. Important services identified included:

- 111/tcp – rpcbind

- 2049/tcp – NFS

These results indicated that the NFS service was available for further enumeration.

## **Step 3: Enumerate the NFS Service**

### **Command**

nmap -sC -sV -p 2049,111 --script nfs* 192.168.1.46

### **Explanation**

- -p 2049,111 → Scans NFS-related ports.

- --script nfs* → Executes NFS enumeration scripts.

### **Purpose**

To collect detailed information regarding:

- NFS configuration

- Exported shares

- Accessible directories

- Available NFS resources

### **Observation**

The enumeration process confirmed the presence of NFS shares and provided information about resources available through the NFS service.

## **Step 4: Create a Local Mount Point**

### **Command**

mkdir /mnt/nfs1

### **Purpose**

Creates a local directory that will be used as the mount point for the remote NFS share.

## **Step 5: Mount the NFS Share**

### **Command**

mount -t nfs 192.168.1.46:/ /mnt/nfs1

### **Explanation**

- mount → Mounts a filesystem.

- -t nfs → Specifies the NFS filesystem type.

- 192.168.1.46:/ → Remote NFS share.

- /mnt/nfs1 → Local mount directory.

### **Purpose**

To connect the remote NFS share to the Kali Linux machine and access its contents locally.

## **Step 6: Access the Mounted Share**

### **Command **

cd /mnt/nfs1

ls

### **Purpose**

Displays the files and folders available within the mounted NFS share.

## **Step 7: Navigate to the Shared Home Directory**

### **Command**

cd home

### **Purpose**

Moves into the shared home directory exported through NFS.

## **Step 8: Create a New Directory**

### **Command**

mkdir gr8

### **Purpose**

Creates a new folder named **gr8** inside the mounted NFS share.

## **Step 9: Verify Directory Creation**

### **Command**

ls

### **Purpose**

Confirms that the newly created directory exists within the mounted share.

## **Step 10: Verify from the Metasploitable Machine**

### **Commands**

cd /home

ls

mkdir gr8

### **Purpose**

To verify that the directory created from Kali Linux is also visible on the Metasploitable system.

## **Why Did This Happen?**

The mounted directory on Kali Linux is directly linked to the shared NFS directory on the Metasploitable machine.

/mnt/nfs1 (Kali Linux)

 ↓

Mounted NFS Share

 ↓

/home (Metasploitable)

Since both systems are accessing the same shared location:

- Changes made from Kali Linux are reflected on Metasploitable.

- Files and folders created on one system become visible on the other.

- Both systems interact with the same shared directory structure.

## **Understanding NFS**

### **What is NFS?**

NFS (Network File System) is a file-sharing protocol that allows Linux and Unix-based systems to share directories and files across a network.

### **Advantages of NFS**

- Centralized file sharing

- Easy resource access across systems

- Simplified data management

- Efficient collaboration between hosts

## **Observation**

The NFS service running on the target machine was successfully identified and enumerated. Exported shares were discovered, and the remote share was mounted on the Kali Linux system. A new directory was created through the mounted share and was successfully verified on the Metasploitable machine, confirming read and write access to the shared resource.
