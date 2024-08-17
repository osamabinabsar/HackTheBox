# Nibbles machine notes from walkthroughs

- HackerSploit used bash reverse shell and transferred it to the vulnerable machine for prvelege escalation.
  - Privelege excalation with kernel exploit
  - Used search exploit to find vulnerability
  - Used Google to find scripts
  - linux exploit suggester script
  - _One should be careful with kernel exploits or while testing out kernel vulns as it can cause kernel panic or system to crach_
  - searched for exploits with version > midfied with attacking ip > transferred t to victim ip > ./exploit > tadaa!
  - compiled the exploit with gcc

##### TheCyberMentor
- One should not be too specific, otherwise susprises may be missed
- Another technique he showed that there was no personal or stuff folder, but a personal.zip folder. Therefore, we can create out own monitor.sh and upload it and run it without unzipping the monitor.sh doc.
- Cunning way to get root shell, he ech9oed "bash -i" > monitor.sh, what it will do it when we run monitor.sh, it will execute bash -i, as mointor.sh is sudo, bash -i will run as sudo, thus giving us the root access.
- sudoing full path worked, therefore, while pentesting ew should not get hopeless and try other ways.
- ![image](https://github.com/user-attachments/assets/075abf12-de54-4f4e-a964-7315b2657126)


##### Ippsec
