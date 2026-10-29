# Stapler: 1 — VulnHub Write-up

## Box info

- **Platform:** VulnHub
- **Target:** Stapler: 1
- **Environment:** Kali Linux and VirtualBox

## Enumeration

An Nmap service scan identified the following open ports:

| Port | Service | Version / Details |
|---|---|---|
| 21 | FTP | vsftpd 3.0.3 |
| 22 | SSH | OpenSSH 7.2p2 |
| 53 | DNS | dnsmasq 2.75 |
| 80 | HTTP | Web service |
| 139 | SMB | Samba 4.3.9 |
| 666 | Unknown | ZIP-like data detected |
| 3306 | MySQL | MySQL 5.7.12 |

Anonymous FTP access and SMB enumeration provided additional information about the target.

## Initial Access

Further enumeration revealed WordPress-related files and user information. A PHP reverse shell was uploaded to the web-accessible uploads directory and executed.

## Privilege Escalation

Local enumeration revealed user accounts and a privilege-escalation opportunity involving the `peter` account. The account's sudo permissions allowed execution of commands as root.

## Proof of Root Access

The root flag was found in `/root/flag.txt`.

<img width="959" height="729" alt="flag" src="https://github.com/user-attachments/assets/9e4801b8-026e-4bba-ba0a-0b8c4a695940" />

## Lessons Learned

- Initial NMAP scans are super important as it reveals the borders of the puzzle needed to be solved.
- Vulnerabilities assessed as low or medium can lead to discovery of critical vulnerabilities.
- Reviewing file permissions and configuration files is key in finding information. 
- Check sudo permissions during local privilege-escalation enumeration.
