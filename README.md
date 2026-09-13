Mediroza General Hospital — Web Application Penetration Test

Type: Black-box penetration test (authorized training engagement) Program: Networkwalks Cybersecurity Internship — Batch B082, Week 4 Capstone Mentor: Waqas Karim, CCIE Status: Complete ✅

Overview

A full black-box assessment of a simulated hospital web application, tracing a single low-severity observation all the way to a critical, organization-wide data exposure. This project was built to practice not just finding vulnerabilities, but chaining them the way a real attacker would.

Attack Chain
Recon (robots.txt)
   └─▶ Username enumeration on login page
         └─▶ SQL injection → full authentication bypass
               └─▶ Access to confidential patient report PDFs
                     └─▶ Weak PDF passwords cracked via wordlist attack
                           └─▶ Metadata leak reveals internal backup path
                                 └─▶ Exposed directory listing (/old)
                                       └─▶ Plaintext DB backup: 30 salaries + 10 shareholder records
Key Findings
#	Vulnerability	Severity
1	Username enumeration	Medium
2	SQL injection (auth bypass)	Critical
3	Confidential PDFs exposed post-bypass	High
4	Weak, crackable PDF passwords	High
5	Sensitive metadata left in PDFs	Medium
6	Directory listing enabled on backup folder	Critical
7	Plaintext salary & shareholder data in DB backup	Critical
Tools Used

curl · Browser DevTools · qpdf · exiftool · wget · custom hash/password cracking utilities

What This Project Demonstrates
Manual SQL injection identification and exploitation (no automated scanners)
Real-world impact of "minor" misconfigurations when chained together
Metadata analysis as a reconnaissance vector
Clear, evidence-based technical writing and remediation guidance
Disclaimer

This assessment was performed in a fully controlled, authorized environment as part of an educational internship. No real systems, patients, or organizations were involved. These techniques must never be used against any system without explicit written authorization.
