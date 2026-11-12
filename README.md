# Penetration Testing Report
Footprinting and network scanning phases

| Name of Pentester               | Chrizlen Dave P. Rollan                                                                          |
|---------------------------------|--------------------------------------------------------------------------------------------------|
| Batch                           | BO84-NETWORKWALKS                                                                                |
| Modules Completed               | W2-PM4 (Footprinting and Reconnaissance with theHarvester) W2-PM5 (Network scanning with Zenmap) |
| Client/Target                   | Microsoft (with letter of permission) Personal Network                                           |
| Permission secured from client? | Yes                                                                                              |
| Date                            | 09 November 2026                                                                                 |
| Phases covered                  | Phase 1: Reconnaissance & Footprinting Phase 2: Scanning & Network Discovery                     |

### 1. Liability Disclaimer
The following tasks are done within the scope of this penetration testing project and are only done for education and research purposes, without the intent of doing any harm. To confirm the legality of this penetration testing project, I have secured written permission from the company to ensure that I agree to and must follow all the rules and regulations of this project. Every action I take is my own responsibility, and any misuse of tools that can lead to criminal charges, loss of job, or a permanent record is not the responsibility of NetworkWalks. 

### 2. Introduction
This penetration testing report covers the use of Footprinting and reconnaissance using theHarvester on the Kali Linux virtual machine and Network Scanning using the Zenmap Nmap tool. As an intern at NetworkWalks, learning to master these penetration testing techniques will serve as a huge help when it comes to real-world situations. Learning to master footprinting and reconnaissance using theHarvester will help me with finding website vulnerabilities, and learning to master network scanning will help me learn to identify suspicious users on the network. All activities were performed on the Kali Linux virtual machine for footprinting and on Windows 11, my main computer’s operating system, for Zenmap. 

### 3. Tools Used
| Tool          | Purpose                                                                   |
|---------------|---------------------------------------------------------------------------|
| Kali Linux    | Used as my main os for footprinting with TheHarvester                     |
| TheHarvester  | Used to collect emails, hosts, and domains from public sources            |
| Baidu         | A public search engine data source that TheHarvester uses to collect info |
| Windows 11    | My main computer’s os for network scanning using Zenmap                   |
| Zenmap (Nmap) | Scans my LAN to spot active hosts’ IP addresses and MAC addresses         |
| Windows CMD   | Used the ipconfig command to find my computer’s IPv4 address              |

### 4. Activities Performed
#### 4.1. Footprinting and Reconnaissance
Using theHarvester on the Kali Linux virtual machine, I performed footprinting and reconnaissance on microsoft.com to discover emails, hosts, and domains related to the targeted website from public sources. 

Using the command “theHarvester -d microsoft.com -l 1000 -b baidu” in the Kali Linux terminal with Baidu as the data source, I discovered 4 emails and 13 hosts associated with the target website. These may not be much, but any of these discovered emails and hosts could be a potential vulnerability for Microsoft, so it's best these aren’t left ignored. 

I want to look a little deeper this time, so using the command “theHarvester -d microsoft.com -l 50 -b all”, with “all” as the main data source, I discovered 14 IP addresses, 3 emails, and 9,963 hosts. It took a while to discover this much information, but this many discovered hosts reveal the true scale of Microsoft’s attack surface. Having thousands of hosts is in the normal range, but this activity reveals the attack surface of an organization and the potential targets of cyber attackers.

#### 4.2. Network Scanning
For the second activity, I scanned my Local Area Network using Zenmap, an Nmap application used to discover active hosts and their IP and MAC addresses inside a LAN. Nmap can also be run inside the Kali Linux virtual machine through the terminal, but for this activity, I will be using the Zenmap application on my main operating system (Windows 11) to perform an Nmap scan. 
First, I opened up my Windows CMD and typed in the command “ipconfig /all” to discover my computer’s IPv4 address, which I will be using for my Nmap scan. After grabbing my computer’s IPv4 address, I copied and pasted the address into Zenmap as its targeted IP with /24 as its subnet mask. I then set the profile to “Ping Scan” before clicking on the scan button to start searching. 

The Nmap scan discovered 5 different hosts on my LAN that were active during the scanning process. The following are the discovered IPv4 addresses active on my local network: 
- 192.168.70.137
- 192.168.70.146
- 192.168.70.147
- 192.168.70.148
- 192.168.70.131

To save the results, I opened Topology, enabled the legend, and saved the results as a PDF file for documentation purposes. 

### 5. Risk Analysis 
The following table contains the potential risks and their risk levels based on the collected information from my footprinting and network scanning activities, not confirmed vulnerabilities: 

| Risk                                           | Evidence                                                                                                                    | Potential Impact                                                                                           | Risk Level |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|------------|
| Corporate email addresses exposed              | TheHarvester discovered multiple email addresses through public search engines                                              | Potential risk of spear-phishing and social engineering attacks against employees.                         | Medium     |
| Large-scale exposure of IP addresses and hosts | TheHarvester uncovered 14 IP addresses and 9,963 hosts during reconnaissance                                                | Increases the overall attack surface, giving attackers a better chance of exploiting vulnerabilities.      | High       |
| Information leakage                            | TheHarvester, through passive reconnaissance, successfully retrieved organizational information without triggering alerts.  | Provides attackers a blueprint that maps out the entire infrastructure without alerting the organization.  | Medium     |
| LAN host visibility                            | Zenmap ping scan detected 5 active internal host IPs within the local subnet.                                               | Unauthorized users could map the local network through unauthorized scanning and other possible attacks.   | Medium     |

### 6. Recommendations
The following are the recommendations made based on the risks listed above and how an organization can mitigate them.
#### 1. Keep software up to date
Ensures security stays up to date, lowering the risk of data loss and damage from cyber attacks. 
#### 2. Reduce host visibility and email exposure
Exposed hosts and emails increase an organization’s attack surface. Implement strict email security policies and reduce unnecessary public DNS records to reduce the attack surface. 
#### 3. Conduct employee security awareness training
Unaware employees increase the risk of human error, so security awareness training is recommended to help employees stay aware of possible cyber attacks. 
#### 4. Secure LAN visibility 
Implement proper network segmentation, and enable your computer’s firewall to block ICMP echo requests. 
#### 5. Prevent Passive Information Leakage
Harden web servers and DNS configurations to limit banner grabbing and metadata exposure.

### 7. Conclusion
For my second week as an intern at NetworkWalks, I have completed activities that center around footprinting and reconnaissance, and network scanning. 

For my first activity, I used the Kali Linux terminal on my virtual machine to start up theHarvester, a footprinting and reconnaissance tool used to gather information about an organization such as emails, hosts, and domains. Using different commands, I discovered thousands of hosts from my chosen organization, highlighting a large attack surface.

This made me realize how important it is to reduce host visibility to help lower the attack surface.

For my second activity, I used my computer’s main OS (Windows 11) to run an Nmap scan in Zenmap. After ping-scanning my LAN, I found 5 active IPv4 addresses on my network. This also made me realize the importance of securing LAN visibility. 

I overall enjoyed this new experience, and I can’t wait to see what tasks week 3 has to offer me 🚀

