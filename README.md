# Room Overview
Room Name: Agent T
Difficulty: Easy
Theme: Web exploitation & privilege escalation
Description: “Something seems a little off with the server.”
Target System: Linux server running a vulnerable PHP version
Tools Commonly Used:
Recon: nmap, ffuf, gobuster
Exploitation: ExploitDB scripts, Burp Suite, curl
Post-Exploitation: linpeas, manual enumeration


🔑 Key Learning Points
Reconnaissance
Nmap scan reveals port 80 open with a PHP web server running PHP 8.1.0-dev.
This version is suspicious because it’s a development build, not meant for production.

Vulnerability Discovery
The server leaks version info in HTTP headers.
Attackers can research vulnerabilities in PHP 8.1.0-dev and discover the “User-Agentt” backdoor.

Exploitation
By sending a malicious User-Agentt header, arbitrary system commands can be executed.
Example: Using ExploitDB PoC (49933), attackers gain a pseudo shell directly as root.

Privilege Escalation
Unlike many rooms requiring privilege escalation, here the exploit provides root access immediately.
The flag is found in /root/flag.txt.

#The TryHackMe room Agent T is an easy-level Linux CTF challenge focused on exploiting a critical vulnerability in PHP 8.1.0-dev, which contains a hidden backdoor allowing attackers to gain remote code #execution (RCE). The room simulates a real-world scenario where a misconfigured server exposes sensitive version information, leading to compromise.
