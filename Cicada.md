# Cicada ![Cicada](https://github.com/user-attachments/assets/9141d564-ca50-4774-a65c-7654aa3aaadc)






### Enumeration
#### Nmap






















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
