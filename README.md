# cybersec-task1
Documentation and findings from my cybersecurity internship
Cybersecurity Project – Port Scan Analysis
📌 Project Overview
This repository documents the findings from a port scanning activity conducted as part of a cybersecurity internship. The objective is to identify open ports on a target system, understand the services running on these ports, assess potential security risks, and recommend mitigation strategies.

🖥️ Target System Details
IP Address: 192.168.xxx.x

Subnet Mask: 255.255.255.0 (CIDR Notation: /24)

🛠️ Tools Utilized
Port Scanning: Nmap

Operating System: Windows 10

📄 Open Ports Identified
The following TCP ports were found to be open on the target system:

Port	Service	Description
22	SSH	Secure Shell for encrypted remote login and command execution. Learn more
80	HTTP	Hypertext Transfer Protocol for unencrypted web traffic. Learn more
139	NetBIOS-SSN	NetBIOS Session Service for file and printer sharing over a network. Learn more
445	Microsoft-DS (SMB)	Server Message Block protocol for sharing files and printers. Learn more

🔍 Analysis & Security Implications
Port 22 – SSH
Purpose: Enables secure remote login and command execution.

Security Considerations:

Brute-force Attacks: Attackers may attempt to guess login credentials.

Outdated Software: Vulnerabilities in outdated SSH versions can be exploited.

Recommendations:

Use strong, unique passwords or SSH keys for authentication.

Disable root login over SSH.

Change the default SSH port from 22 to a non-standard port to reduce automated attacks.

Regularly update SSH software to the latest version.

Port 80 – HTTP
Purpose: Facilitates unencrypted web traffic.

Security Considerations:

Data Interception: Information transmitted is in plaintext and can be intercepted.

Man-in-the-Middle Attacks: Lack of encryption makes it susceptible to interception and modification.

Recommendations:

Redirect HTTP traffic to HTTPS (port 443) to ensure encryption.

Obtain and install a valid SSL/TLS certificate.

Regularly update web server software to patch known vulnerabilities.

Port 139 – NetBIOS-SSN
Purpose: Supports file and printer sharing over a network using NetBIOS over TCP/IP.

Security Considerations:

Information Leakage: May expose sensitive information about the network.

Unauthorized Access: Can be exploited to gain unauthorized access to shared resources.

Recommendations:

Disable NetBIOS over TCP/IP if not required.

Block port 139 at the network perimeter using firewalls.

Ensure that file and printer sharing is disabled on public networks.

Port 445 – Microsoft-DS (SMB)
Purpose: Used for sharing files, printers, and serial ports over a network.

Security Considerations:

WannaCry & NotPetya: Notorious ransomware attacks exploited vulnerabilities in SMB.

Remote Code Execution: Vulnerabilities can allow attackers to execute arbitrary code.

Recommendations:

Disable SMBv1 protocol; use SMBv2 or SMBv3.

Block port 445 at the network perimeter.

Apply the latest security patches from Microsoft.

Use network segmentation to limit exposure.
