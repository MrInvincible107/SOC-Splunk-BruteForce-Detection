\# SOC Detection Engineering (Splunk + Wireshark)



Overview

This project demonstrates detection of brute force login attempts using Splunk and correlates findings with network traffic analysis using Wireshark.



Tools Used

\- Splunk Enterprise

\- Wireshark

\- Windows Event Logs



Objectives

\- Detect brute force login attempts

\- Analyze authentication failures

\- Correlate log data with network traffic

\- Simulate real-world SOC investigation



Detection Approach



\- Event ID 4625 → Failed login attempts

\- Event ID 4740 → Account lockout

\- Threshold-based detection using Splunk



Dashboard Features



\- Failed login attempts over time

\- Top targeted accounts

\- Alert triggering system



Investigation Summary



\- Multiple failed login attempts detected

\- Target user identified

\- Account lockout confirmed



Network Analysis



\- Traffic analyzed using Wireshark

\- High UDP traffic identified as QUIC (HTTP/3)

\- DNS traffic showed normal domains (Google, Cloudflare)



Key Takeaways



\- High traffic ≠ malicious activity

\- Context-based analysis is critical

\- Detection requires both logs + network visibility



MITRE ATT\&CK Mapping



This project maps detection logic to MITRE ATT\&CK framework:



\- \*\*T1110 – Brute Force\*\* → Failed login attempts (Event ID 4625)

\- \*\*T1071 – Application Layer Protocol\*\* → HTTPS/QUIC traffic observed



See detailed mapping in:

`detection/mitre\_mapping.md`

Sigma Rule

A Sigma rule was created to detect brute force login attempts based on Windows Security logs.

Detection Logic
- Event ID 4625 (failed login)
- Threshold-based detection (5 attempts in 5 minutes)

See: `detection/bruteforce_sigma_rule.yml`


Conclusion

Successfully simulated and detected a brute force attack and validated findings using network traffic analysis.

