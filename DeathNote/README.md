# Deathnote: 1 — VulnHub

A penetration-testing assessment of the Deathnote: 1 vulnerable Linux machine from VulnHub.

## Overview

- **Platform:** VulnHub
- **Machine:** Deathnote: 1
- **Target IP:** `192.168.56.111`
- **Hostname:** `deathnote.vuln`
- **Operating System:** Debian GNU/Linux
- **Difficulty:** Beginner
- **Status:** Completed

## Methodology

1. Network reconnaissance and service enumeration.
2. Web server and WordPress enumeration.
3. Discovery of exposed files and information disclosure.
4. Analysis of encoded data (Brainfuck, hexadecimal and Base64).
5. SSH credential discovery and initial access.
6. Local enumeration and user investigation.
7. Privilege escalation through misconfigured sudo permissions.
8. Root access verification.

## Tools Used

- Nmap
- WPScan
- Hydra
- SSH
- Linux command-line utilities
- Encoding and decoding tools

## Key Findings

- Exposed WordPress resources and directory listing.
- Information disclosure through publicly accessible files.
- Encoded clues containing sensitive information.
- Weak SSH credentials.
- Unrestricted sudo permissions allowing privilege escalation.
