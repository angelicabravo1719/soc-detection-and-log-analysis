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
Get-Location
Get-Process
```

---

## What I Observed

PowerShell provides direct access to system information and administrative functions.

Commands executed successfully and returned information about:

* The current user.
* The current working directory.
* Running processes on the system.

PowerShell output is displayed directly within the terminal and can be used to automate administrative and investigative tasks.

---

## Evidence Collected

### Screenshots

Store screenshots in:

```text
screenshots/lab-03-suspicious-powershell-activity/
```

Suggested files:

```text
powershell_user_context.png
powershell_process_review.png
```

---

## Investigation Findings

### User Context

The PowerShell session identified the currently logged-in user account.

### Working Directory

The current execution location was identified using PowerShell.

### Process Review

Running processes were reviewed using PowerShell commands.

### Security Analysis

The commands executed during this lab are commonly observed during legitimate administrative activity. However, similar commands are also frequently used by attackers during system discovery and reconnaissance phases.

### Conclusion

PowerShell activity was reviewed in a controlled lab environment. The commands executed gathered local system information and demonstrated how administrative actions can generate activity that may later be reviewed during security investigations.

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
