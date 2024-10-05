# Cicada ![Cicada](https://github.com/user-attachments/assets/9141d564-ca50-4774-a65c-7654aa3aaadc)






### Enumeration
#### Nmap
            ──╼ #nmap -p- -sC -sV -sS --script=vuln -O -A 10.10.11.35
            Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-10-05 13:07 EEST
            Nmap scan report for cicada.htb (10.10.11.35)
            Host is up (0.047s latency).
            Not shown: 65522 filtered tcp ports (no-response)
            PORT      STATE SERVICE       VERSION
            53/tcp    open  domain        Simple DNS Plus
            88/tcp    open  kerberos-sec  Microsoft Windows Kerberos (server time: 2024-10-05 17:12:38Z)
            135/tcp   open  msrpc         Microsoft Windows RPC
            139/tcp   open  netbios-ssn   Microsoft Windows netbios-ssn
            389/tcp   open  ldap          Microsoft Windows Active Directory LDAP (Domain: cicada.htb0., Site: Default-First-Site-Name)
            445/tcp   open  microsoft-ds?
            464/tcp   open  kpasswd5?
            593/tcp   open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
            636/tcp   open  ssl/ldap      Microsoft Windows Active Directory LDAP (Domain: cicada.htb0., Site: Default-First-Site-Name)
            3268/tcp  open  ldap          Microsoft Windows Active Directory LDAP (Domain: cicada.htb0., Site: Default-First-Site-Name)
            3269/tcp  open  ssl/ldap      Microsoft Windows Active Directory LDAP (Domain: cicada.htb0., Site: Default-First-Site-Name)
            5985/tcp  open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
            |_http-server-header: Microsoft-HTTPAPI/2.0
            |_http-stored-xss: Couldn't find any stored XSS vulnerabilities.
            |_http-csrf: Couldn't find any CSRF vulnerabilities.
            |_http-dombased-xss: Couldn't find any DOM based XSS.
            58431/tcp open  msrpc         Microsoft Windows RPC
            Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
            Device type: general purpose
            Running (JUST GUESSING): Microsoft Windows 2022 (89%)
            Aggressive OS guesses: Microsoft Windows Server 2022 (89%)
            No exact OS matches for host (test conditions non-ideal).
            Network Distance: 2 hops
            Service Info: Host: CICADA-DC; OS: Windows; CPE: cpe:/o:microsoft:windows
            
            Host script results:
            |_smb-vuln-ms10-061: Could not negotiate a connection:SMB: Failed to receive bytes: ERROR
            |_smb-vuln-ms10-054: false
            |_samba-vuln-cve-2012-1182: Could not negotiate a connection:SMB: Failed to receive bytes: ERROR
            
            TRACEROUTE (using port 139/tcp)
            HOP RTT      ADDRESS
            1   51.05 ms 10.10.14.1
            2   51.10 ms cicada.htb (10.10.11.35)
            
            OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
            Nmap done: 1 IP address (1 host up) scanned in 678.47 seconds





















----------------------------------------------

**NXC (Network eXploitation Command)** typically refers to tools or commands used in network exploitation, often associated with SMB (Server Message Block) for file sharing and other services in Windows environments. However, it’s important to remember that there are many other protocols to explore, such as:

1. **WinRM (Windows Remote Management):**
   - This protocol allows for remote management of Windows machines. It uses WS-Management and can provide access to various services and scripts running on a remote system. By probing WinRM, you can gather information about the target's services, configurations, and even execute commands remotely.

2. **LDAP (Lightweight Directory Access Protocol):**
   - LDAP is used for accessing and maintaining distributed directory information services. It’s commonly employed in Active Directory environments. By querying LDAP, you can retrieve valuable information about user accounts, groups, and permissions, which can help in understanding the security posture of the organization.

### Why Explore Other Protocols?
- **Different Outputs:** Each protocol can provide different types of data or responses, which can lead to a deeper understanding of the target system.
- **Security Vulnerabilities:** Different protocols might have unique vulnerabilities or misconfigurations that can be exploited. For example, unsecured WinRM endpoints or misconfigured LDAP permissions can be entry points for attackers.
- **Comprehensive Assessment:** By not limiting your focus to just SMB, you can create a more comprehensive assessment of the security landscape.

### Diving Deeper with Other Parameters
When exploring these protocols, consider varying parameters and options to get richer data:
- **Authentication Methods:** Test different authentication methods (e.g., NTLM, Kerberos) to see what works.
- **Filters and Queries:** Modify LDAP queries or WinRM commands to refine the information you retrieve.
- **Service Enumeration:** Use specific commands to enumerate services running over these protocols for insights into their configurations and potential weaknesses.

By broadening your scope beyond just SMB to include protocols like WinRM and LDAP, you can uncover a more nuanced view of your target environment, which is crucial for effective security assessments.



`Actually, it’s a cool box. All you guys need to do is pay attention to the outputs of your enumeration tools. Just stuggle beacuse of a non-sense missing of the credentials running infront of my eyes for 10 times.

`Foothold: Enumerate the available services; it’s all there. When you don’t have usernames, you can obtain them through other numerical enumeration assigned to them. After obtaining credentials, recycle the same enumeration process using common utilities and pay attention to the outputs, as they will reveal the next user. Repeat this process. Then you will have a foothold.

`Root: Pay attention to your tokens. Easy root.
