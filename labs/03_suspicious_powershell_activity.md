# 03 — Suspicious PowerShell Activity

## Goal

Understand how PowerShell can be used for system administration and automation while also recognizing why it is frequently abused by attackers.

PowerShell is one of the most commonly observed tools during cybersecurity investigations because it provides direct access to system functionality and can execute commands, scripts, and administrative tasks.

---

## What I Did

* Executed PowerShell commands in a controlled lab environment.
* Reviewed PowerShell activity and command execution.
* Observed system information gathering commands.
* Documented command output and behavior.
* Evaluated how PowerShell activity may appear during a security investigation.

---

## Tools Used

### Windows PowerShell

Used to execute administrative and information-gathering commands.

### Commands Used

```powershell
whoami
hostname
Get-Location
Get-Process
ipconfig
```

---

## What I Observed

PowerShell successfully executed a series of system discovery commands commonly used by administrators and security analysts.

The commands revealed:

* The currently logged-in user account.
* The hostname of the workstation.
* The current working directory.
* Running processes on the system.
* Network configuration information.

The commands executed without errors and returned information directly from the local Windows system.

---

## Evidence Collected

### Screenshots

Store screenshots in:

```text
screenshots/lab-03-suspicious-powershell-activity/
```

Files:

```text
powershell_user_context.png
powershell_network_review.png
```

---

## Investigation Findings

### User Enumeration

Command:

```powershell
whoami
```

Result:

```text
angie_pc\angel
```

This identified the currently logged-in user account.

### Host Discovery

Command:

```powershell
hostname
```

Result:

```text
Angie_PC
```

This identified the system hostname.

### Working Directory Review

Command:

```powershell
Get-Location
```

Result:

```text
C:\Users\angel
```

This identified the current PowerShell execution location.

### Process Enumeration

Command:

```powershell
Get-Process
```

This returned a list of running processes, including:

```text
AdobeCollabSync
ApplicationFrameHost
backgroundTaskHost
Canva
```

Process enumeration is commonly used by administrators and analysts to understand what applications and services are running on a system.

### Network Configuration Review

Command:

```powershell
ipconfig
```

Key observations:

```text
IPv4 Address: 10.111.28.28
Subnet Mask: 255.255.192.0
Default Gateway: 10.111.0.1
DNS Suffix: p.fiu.edu
```

This command provided information about the workstation's network configuration and connectivity.

### Security Analysis

The sequence of commands executed during this lab resembles system discovery activity frequently observed during the early stages of security investigations.

Commands such as:

```powershell
whoami
hostname
Get-Location
Get-Process
ipconfig
```

are commonly used by:

* System Administrators
* Security Analysts
* Incident Responders

However, similar commands may also be used by attackers to gather information about a system after gaining access.

### Conclusion

PowerShell was used to gather user, host, process, and network information from the local system. The activity demonstrated how legitimate administrative commands can closely resemble reconnaissance techniques reviewed during cybersecurity investigations. No malicious activity was identified, and all commands were executed during a controlled lab exercise.

---

## Security Relevance

PowerShell is frequently used by:

* System Administrators
* Security Analysts
* Incident Responders
* Threat Hunters
* Adversaries

Common uses include:

* System administration
* Process investigation
* User enumeration
* System discovery
* Automation
* Incident response

---

## Key Takeaways

* PowerShell provides powerful access to Windows system functionality.
* Administrative commands can generate activity reviewed during investigations.
* PowerShell is commonly used for both legitimate and malicious purposes.
* Security analysts frequently investigate PowerShell activity during incident response.
* Understanding PowerShell behavior is an important SOC analyst skill.

---

## Note

This lab was performed in a personal lab environment for educational and portfolio development purposes.
