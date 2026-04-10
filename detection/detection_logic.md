**Brute Force Detection Logic**



Data Source

Windows Security Event Logs



Key Events

\- Event ID 4625 → Failed login

\- Event ID 4740 → Account lockout



Detection Strategy

Multiple failed login attempts within a short period indicate brute force activity.



SPL Query

See splunk\_queries.spl



Rationale

\- Repeated failures = suspicious behavior

\- Threshold helps reduce false positives



Limitations

\- Users may mistype passwords

\- Distributed attacks may evade detection

