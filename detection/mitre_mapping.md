MITRE ATT\&CK Mapping



Overview

This project maps detected brute force activity and network observations to MITRE ATT\&CK techniques.



Credential Access



Technique: Brute Force

\- \*\*ID:\*\* T1110

\- \*\*Tactic:\*\* Credential Access



Description

Adversaries attempt to gain access by trying multiple username/password combinations.



Evidence in Project

\- Multiple failed login attempts (Event ID 4625)

\- Threshold-based detection in Splunk

\- Repeated authentication failures for same account



Account Access Impact



Technique: Account Lockout (Defensive Outcome)

\- \*\*Event ID:\*\* 4740



Description

System triggered account lockout due to repeated failed login attempts.



Evidence

\- Lockout observed after multiple failed attempts

\- Confirms brute force behavior



Network Behavior



Technique: Application Layer Protocol

\- \*\*ID:\*\* T1071

\- \*\*Tactic:\*\* Command and Control



Description

Adversaries may use standard protocols like HTTP/HTTPS for communication.



Evidence in Project

\- Observed traffic over port 443 (HTTPS)

\- QUIC protocol (HTTP/3 over UDP)

\- DNS queries to external domains



Analysis

\- Traffic determined to be normal (Google/Cloudflare)

\- No malicious C2 behavior detected



Detection Summary



| Technique | ID | Evidence |

|----------|----|---------|

| Brute Force | T1110 | Event ID 4625 spikes |

| Application Layer Protocol | T1071 | HTTPS/QUIC traffic |

| Account Lockout | N/A | Event ID 4740 |



Key Insight



Mapping detections to MITRE ATT\&CK helps:

\- Standardize threat detection

\- Improve SOC analysis capability

\- Communicate findings effectively



Conclusion



The project successfully demonstrates detection of brute force activity mapped to MITRE ATT\&CK techniques, with supporting log and network evidence.

