# Incident Report: Brute Force Login Attempt

## Incident Summary
Multiple failed login attempts were detected against a single user account within a short time window. The activity originated from a single external IP address and did not result in a successful authentication.

## Log Analysis
Windows Security Event Logs (Event ID 4625) showed repeated failed authentication attempts from a single IP address. No successful login events (Event ID 4624) were observed following the failures.

## Analyst Assessment & Decision
The activity was assessed as a low to medium severity brute force attempt. Since no account compromise occurred, the incident was documented and closed with monitoring recommendations.

## MITRE ATT&CK Mapping
T1110 – Brute Force

## Final Notes
This incident highlights the importance of monitoring authentication logs to detect potential credential-based attacks early.

## Detection Logic (SIEM – Splunk)

```spl
index=windows EventCode=4625
| stats count by Account_Name, src_ip
| where count > 10
```
This query detects multiple failed login attempts associated with the same user account and source IP and applies a threshold to reduce false positives from normal user behavior.

