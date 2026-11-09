# RickdiculouslyEasy – VulnHub

## Overview

This repository documents my penetration-testing assessment of **RickdiculouslyEasy**, an intentionally vulnerable virtual machine from VulnHub.

## Lab Information

| Attribute | Details |
|---|---|
| Machine | RickdiculouslyEasy |
| Target IP | `192.168.56.112` |
| Attacker Machine | Kali Linux |
| Assessment Type | Controlled Lab Penetration Test |
| Final Access | Root |

## Methodology

### 1. Web Enumeration
### 2. Information Gathering
### 3. SSH Credential Discovery
### 4. Post-Exploitation Enumeration
### 5. Privilege Escalation
## Tools Used

| Tool | Purpose |
|---|---|
| Nmap | Network and service enumeration |
| Gobuster | Web directory enumeration |
| Hydra | SSH password testing |
| Crunch | Password candidate generation |
| SSH | Remote access |
| SCP | File transfer |
| Linux utilities | File inspection and post-exploitation enumeration |

## Key Findings

- Exposed web directories and files.
- Information disclosure through web application functionality.
- Weak SSH authentication.
- Sensitive information accessible through user files.
- Unrestricted sudo privileges allowing root-level access.

