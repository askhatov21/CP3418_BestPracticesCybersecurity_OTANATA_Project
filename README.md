# CP3418_BestPracticesCybersecurity_OTANATA_Project
CVE-2024-3273 — Authorized Penetration Test Report D-Link DNS-320L NAS | Client: Otonata
<img width="651" height="401" alt="Снимок экрана 2026-04-25 в 5 15 52 PM" src="https://github.com/user-attachments/assets/9a942070-af33-44cf-831f-d2c86f8fa7f7" />
<img width="587" height="154" alt="Снимок экрана 2026-04-25 в 5 15 44 PM" src="https://github.com/user-attachments/assets/51d657d1-4b3f-46fe-b40c-d1e594c82dcb" />
<img width="907" height="500" alt="Снимок экрана 2026-04-25 в 5 15 35 PM" src="https://github.com/user-attachments/assets/363e836f-01e5-4dea-a50f-908c2acaf1c7" />


Overview
This repository contains the full security assessment report for an authorized penetration test conducted on a D-Link DNS-320L NAS device for client Otonata (Mr. Johnny Yap), as part of CP3418 Best Practices in Cybersecurity at James Cook University Singapore.
Role: Web Application & API Security Tester
Date: March 2026
Target: D-Link DNS-320L NAS — /cgi-bin/nas_sharing.cgi endpoint

Vulnerabilities Identified
VulnerabilitySeverityCVEHard-coded Credentials (messagebus account)CRITICALCVE-2024-3272HTTP GET Command Injection (cmd/system parameters)CRITICALCVE-2024-3273

What I Did

Hard-coded Credential Exploitation — Demonstrated unauthenticated access via the messagebus backdoor account through the /cgi-bin/nas_sharing.cgi endpoint
Command Injection — Manipulated cmd and system HTTP GET parameters with Base64-encoded payloads to achieve remote system-level command execution
Shodan OSINT Analysis — Identified 172 globally exposed DNS-320 devices (89 tagged end-of-life) and 4 exposed devices in Singapore across major cloud providers
Security Assessment Report — Produced a structured 57-page report classifying vulnerabilities as HIGH risk with evidence, impact analysis, and remediation recommendations


Tools Used

Kali Linux
Shodan
HTTP GET request manipulation
Base64 encoding/decoding
Burp Suite (basic)


Key Findings
Vulnerability: Hard-coded Credentials
Endpoint: /cgi-bin/nas_sharing.cgi
Parameter: user=messagebus&passwd=
Impact: Full unauthenticated access to NAS system

Vulnerability: Command Injection
Parameters: cmd=15&system=<BASE64_COMMAND>
Impact: Remote arbitrary command execution as root

Shodan Exposure Analysis

172 internet-facing D-Link DNS-320 devices found globally
89 devices tagged as end-of-life (no security patches)
4 exposed devices in Singapore (Alibaba Cloud, Amazon, Microsoft, Vultr)


Disclaimer

This penetration test was conducted in a controlled lab environment on owner-authorized hardware for academic and client purposes only. All testing was performed with explicit written consent from the client (Otonata). Use of these techniques against systems without explicit authorization is illegal and unethical. The author is not responsible for any misuse of this information.


Repository Contents
├── Report_CVE_2024_3273_DNS320L.pdf    # Full 57-page security assessment report
└── README.md

About
Amir Askhatov — Junior Cybersecurity Analyst
Bachelor of Cybersecurity, James Cook University Singapore
LinkedIn | GitHub
