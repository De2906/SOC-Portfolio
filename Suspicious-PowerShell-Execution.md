# Incident Report: Suspicious PowerShell Execution

## Incident Summary
A SIEM alert was triggered due to the execution of PowerShell with encoded command-line arguments on a Windows endpoint.

## Log Analysis
Windows Security Event ID 4688 logs showed PowerShell being launched with the `-EncodedCommand` flag. The process was executed by a standard user account and included obfuscated command content.

## Analyst Assessment & Decision
Encoded PowerShell commands are commonly used to hide malicious activity. Due to the use of encoded arguments and the execution context, this activity was assessed as suspicious and escalated for further investigation.

## MITRE ATT&CK Mapping
T1059.001 – Command and Scripting Interpreter: PowerShell

## Detection Logic (SIEM – Splunk)
```spl
index=windows EventCode=4688
CommandLine="*powershell*"
(CommandLine="*-enc*" OR CommandLine="*-encodedcommand*")
```
