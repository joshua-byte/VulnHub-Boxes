# Stapler: 1 — VulnHub Write-up

## Overview

- **Platform:** VulnHub
- **Target:** Stapler: 1
- **Target IP:** `192.168.56.105`
- **Difficulty:** Beginner
- **Environment:** Kali Linux and VirtualBox
- **Objective:** Practise reconnaissance, enumeration, initial access, and privilege escalation in a controlled lab.

> This write-up documents a deliberately vulnerable virtual machine used for educational purposes in an isolated lab.

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

Further enumeration revealed WordPress-related files and user information. A PHP reverse shell was uploaded to the web-accessible uploads directory and executed, providing a shell as the `www-data` user.

## Privilege Escalation

Local enumeration revealed user accounts and a privilege-escalation opportunity involving the `peter` account. The account's sudo permissions allowed commands to be executed as root.

## Proof of Root Access

Root access was confirmed using `whoami`. The root flag was found in `/root/flag.txt`.

## Key Findings

- Anonymous FTP access was enabled.
- SMB exposed user and file information.
- WordPress-related files and database credentials were discoverable.
- A PHP reverse shell provided initial access as `www-data`.
- Excessive sudo privileges enabled escalation to root.


## Lessons Learned

- Enumerate all exposed services before attempting exploitation.
- Review file permissions and configuration files for sensitive information.
- Check sudo permissions during local privilege-escalation enumeration.
- Document commands, evidence, and security impact at each stage.

## Disclaimer

This write-up is for educational purposes and authorised testing in a controlled lab environment only.
