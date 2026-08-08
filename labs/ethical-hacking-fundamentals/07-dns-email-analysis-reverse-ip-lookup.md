# EH7 — DNS Analysis, Email Analysis & Reverse IP Lookup

**Reverse IP Lookup 

# **4. DNS Information Analysis** using View **Dns**

## **Introduction**

DNS (Domain Name System) is responsible for converting domain names into IP addresses. It helps users access websites using easy-to-remember names instead of numerical IP addresses.

DNS analysis is an important part of information gathering because it provides details about a website's infrastructure and services.

## **Why Analyze DNS Information?**

- Identify server IP addresses

- Discover mail servers

- Understand domain infrastructure

- Identify network services

- Discover subdomains

## **Observation**

DNS analysis provided information about server addresses, mail servers, and domain infrastructure associated with the target website.

# **5. Behind the Email (Email Analysis)**

## **Introduction**

Email Analysis is the process of examining email headers and metadata to determine the origin and path of an email.

The visible sender address may appear legitimate, but technical information is stored within the email header.

## **Information Obtained**

- Sender IP Address

- Mail Server Information

- Authentication Results

- Message Routing Information

- Timestamp Details

## **Why Perform Email Analysis?**

- Identify sender information

- Analyze email transmission paths

- Detect suspicious emails

- Understand email infrastructure

## **What is an Email Header?**

An Email Header contains technical information related to email transmission.

Examples:

- Sender IP Address

- Receiving Mail Servers

- Security Checks

- Delivery Information

## **Observation**

Email analysis revealed technical information related to the sender, mail servers, and email transmission process.

# **6. Reverse IP Lookup**

## **Introduction**

Reverse IP Lookup is a technique used to identify domains hosted on the same IP address.

A single server may host multiple websites, especially in shared hosting environments.

## **Purpose**

- Identify related websites

- Understand hosting infrastructure

- Discover associated domains

- Support information gathering activities

## **Example**

IP Address:

142.250.67.142

Possible Results:

- site1.com

- site2.com

- example.org

## **Methods**

### **Method 1: Online Tools**

Examples:

- ViewDNS

- HackerTarget

### **Method 2: Command Line**

host 142.250.67.142

## **Information Obtained**

- Hosted Domains

- Hosting Type

- Related Infrastructure

- Associated Websites

## **Observation**

Reverse IP Lookup identified domains associated with the target IP address and provided information about the hosting environment.

## **Advantages**

- Identifies related domains

- Helps understand hosting environments

- Useful during reconnaissance

## **Limitations**

- Results may be incomplete

- Shared hosting can produce many unrelated domains

- Information may change over time
