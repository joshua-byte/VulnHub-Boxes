# PwnLab: init — VulnHub

## Overview
This repository documents my penetration-testing assessment of **PwnLab: init**, an intentionally vulnerable VulnHub machine.

The assessment covered web application enumeration, local file inclusion, unsafe file upload handling, initial access, credential investigation, and Linux privilege escalation.

## Lab Environment
- **Attacker:** Kali Linux (`192.168.56.40`)
- **Target:** PwnLab: init (`192.168.56.109`)
- **Application:** PwnLab Intranet Image Hosting
- **Target OS:** Debian Linux (identified from the shell)
- **Network:** VirtualBox host-only lab network

## Attack Path Summary
1. Inspected the web application and discovered exposed database configuration.
2. Identified a cookie-controlled PHP `include()` path that allowed local file inclusion.
3. Uploaded a PHP payload with a GIF suffix through the image-hosting feature.
4. Used the cookie-controlled inclusion path to trigger the payload and obtained a reverse shell as `www-data`.
5. Investigated the `Users` database and local accounts, then accessed the `kane` account.
6. Used the `msgmike` PATH-hijacking weakness to obtain the `mike` account.
7. Exploited unsafe command handling in `msg2root` to obtain root access.

## Key Findings
- Cookie-controlled local file inclusion.
- Unsafe upload handling and exposure of executable content.
- Sensitive database configuration disclosure.
- Reusable account credential material stored in the database.
- Local privilege escalation through `msgmike` and `msg2root`.

## Evidence and Report
- `PwnLab_init_Report.docx` — final assessment report.
- `screenshot_evidence/` — screenshots extracted from the report and numbered in report order.

The report contains the detailed methodology, findings, impact, remediation recommendations, limitations, and figure descriptions.

## Disclaimer
This work was performed in an intentionally vulnerable, isolated lab environment for educational purposes. Do not test these techniques against systems without explicit authorisation.
