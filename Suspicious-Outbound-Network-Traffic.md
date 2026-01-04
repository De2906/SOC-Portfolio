# Incident Report: Suspicious Outbound Network Traffic

## Incident Summary
A SIEM alert was triggered due to suspicious outbound network traffic from a user workstation to an external IP address flagged as potentially malicious.

## Log Analysis
Network and proxy logs showed repeated outbound connections from a single endpoint to an unfamiliar external IP over HTTP. The activity occurred shortly after a PowerShell process execution and was inconsistent with normal user behavior.

## Analyst Assessment & Decision
Outbound connections to unknown external IP addresses following PowerShell execution can indicate malware download or command-and-control activity. Due to the suspicious destination and execution context, this activity was assessed as high risk and escalated for further investigation.

## MITRE ATT&CK Mapping
T1105 – Ingress Tool Transfer

## Detection Logic (SIEM – Splunk)
```spl
index=network_logs
(dest_ip!="internal")
| stats count by src_ip, dest_ip
| where count > 20
```
