## Certifications

☁️ Credential Earned: AWS Cloud Quest: Cloud Practitioner

📜 Issuer: Amazon Web Services (AWS)

🔗 Credential URL: [View Badge on Credly](https://www.credly.com/badges/01a52309-8139-4723-b74e-b89c9476e09a/public_url)

📅 Issued: [06/05/2025]

Description:
This badge recognizes foundational knowledge of AWS Cloud concepts and hands-on experience in building cloud solutions. Earners have demonstrated skills in compute, networking, databases, and security services through interactive learning and solution-building assignments aligned with the Cloud Practitioner role.

🛡️ Credential Earned: CompTIA Security+

📜 Issuer: CompTIA

🔗 Credential URL: [View Badge on Credly](https://www.credly.com/badges/d45c4390-8417-42f7-ad7f-e62afc7c92b1/public_url)

📅 Issued: [05/11/2024]

Description:
The CompTIA Security+ certification validates baseline skills necessary to perform core security functions and pursue an IT security career. It covers essential principles for network security and risk management, including threat analysis, incident response, architecture and design, governance, compliance, and cryptography.
# Home Lab Projects

 I WAS ABLE TO IMPLEMENT SERVER TECHNOLOGY ON MY HOME MACHINE CREATING AND MAINTAINING MY OWN ACTIVE DIRECTORY IMPLEMENTING BASIC SECURITY MEASURES AND I PLAN TO ADD A SIEM AND LEARN SECURITY OPERATIONS MANAGEMENT SKILLS AND ADVANCE MY IT KNOWLEDGE

### HARDENING INCLUDES
1. **Strong Passwords**: Ensure all accounts use strong, complex passwords. This means a mix of uppercase, lowercase, numbers, and special characters.
2. **Regular Updates**: I Keep my AD server on at all times and connected devices updated with the latest security patches and updates.
3. **Limiting Admin Access**: Only My Account has admin access with a Secure complex password.
4. **Enabling Firewall rules**: Made sure the firewall is enabled on my AD server to block unauthorized access.
5. **Backups Regularly**: Regularly back up your AD database and other critical data related to it. then I store the backups in a secure location.
6. **Disable Unnecessary Services**: Turning off any services or features that I do not need. reducing the potential attack surface.
7. **Monitoring Logs**: Regularly checking the event logs for any unusual activity, this can help you detect potential security issues early.
8. **Network Segmentation**: segmenting my network to isolate my AD server from other devices. This adds an extra layer of protection.
### ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## Hacker101 26/26 points
### ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Level 1: Introduction to Web Hacking
- **Understanding Web Applications**: Learn the basics of how web applications work, including HTTP requests and responses, cookies, sessions, and authentication mechanisms.
- **Common Vulnerabilities**: Familiarize yourself with common web vulnerabilities such as Cross-Site Scripting (XSS), SQL Injection, and Cross-Site Request Forgery (CSRF).
- **Burp Suite Basics**: Get comfortable using Burp Suite, a powerful tool for web security testing. Learn how to intercept and modify HTTP traffic.
- **Hacker Mindset**: Cultivate a mindset focused on finding and exploiting vulnerabilities. This involves thinking creatively and understanding how attackers might approach a target.
### ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Level 2: Intermediate Web Hacking
- **Advanced Vulnerabilities**: Dive deeper into more complex vulnerabilities like Remote Code Execution (RCE), Server-Side Request Forgery (SSRF), and Insecure Direct Object References (IDOR).
- **Automated Tools**: Learn to use automated tools and scanners to identify vulnerabilities more efficiently.
- **Report Writing**: Develop skills in writing clear and effective vulnerability reports. This includes detailing the steps to reproduce the issue, the impact, and potential mitigations.
- **Capture the Flag (CTF) Challenges**: Practice your skills through CTF challenges, which simulate real-world hacking scenarios.

### ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
I recently completed a network deployment where I placed a firewall in front of a Cisco router, which then connects to a switch for LAN distribution. Below are the steps I took, including configurations for each device and verification commands.

✅ Topology
[ ISP ] --- [ Firewall ] --- [ Router ] --- [ Switch ] --- [ PCs ]
             WAN: Public IP    WAN: 192.168.0.2
             LAN: 192.168.0.1  LAN: 192.168.1.1

1. Physical Connections

SonicWall X0 → Router FastEthernet0/0
Router FastEthernet0/1 → Switch uplink
PCs → Switch access ports


2. SonicWall Firewall (GUI)

LAN (X0): 192.168.0.1/24
WAN (X1): ISP IP or DHCP
Default Route: 0.0.0.0/0 → ISP Gateway
NAT: LAN→WAN (auto)
Access Rule: Allow LAN→WAN
DHCP: Optional for 192.168.0.x (or disable if router uses static)


3. Cisco 1700 Router
Plain Textenableconfigure terminalhostname Routerenable secret <PASSWORD>!interface FastEthernet0/0 ip address 192.168.0.2 255.255.255.0 no shutdown!interface FastEthernet0/1 ip address 192.168.1.1 255.255.255.0 no shutdown!ip route 0.0.0.0 0.0.0.0 192.168.0.1!ip dhcp excluded-address 192.168.1.1 192.168.1.20ip dhcp pool LAN network 192.168.1.0 255.255.255.0 default-router 192.168.1.1 dns-server 8.8.8.8 1.1.1.1!write memory``Show more lines

4. Switch
Plain Textinterface vlan 1 ip address 192.168.1.2 255.255.255.0 no shutdownip default-gateway 192.168.1.1!interface FastEthernet0/1 switchport mode access switch switchport access vlan 1Show more lines

5. Testing
Plain TextRouter: ping 192.168.0.1, ping 8.8.8.8Switch: ping 192.168.1.1PC: ping 192.168.1.1, pingShow more lines

6. Security Best Practices

Change all default passwords
Restrict management to LAN
Enable SSH on router
Disable unused switch ports
Backup configs
