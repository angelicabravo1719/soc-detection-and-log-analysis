# 01 — Failed Logon Investigation

## Goal

Understand how Windows records failed authentication attempts and learn how security analysts investigate logon failures using Windows Event Viewer.

Failed logon events are among the most commonly reviewed security events within Security Operations Centers (SOCs). Analysts monitor these events to identify password attacks, account misuse, misconfigurations, and unauthorized access attempts.

---

## What I Did

* Generated failed logon attempts by entering an incorrect password at the Windows lock screen.
* Opened Windows Event Viewer.
* Navigated to Windows Security logs.
* Filtered events using Event ID 4625.
* Reviewed failed authentication events.
* Examined event details and authentication metadata.
* Documented findings.

---

## Tools Used

### Event Viewer

Used to review Windows Security event logs.

### Windows Security Logs

Used to investigate authentication activity.

---

## Event ID Investigated

### Event ID 4625

```text
An account failed to log on
```

This event records failed authentication attempts within Windows environments.

---

## What I Observed

The security log contained multiple Event ID 4625 entries generated after intentionally entering an incorrect password.

Key observations included:

* Failed interactive logon attempts.
* Local workstation authentication activity.
* Authentication failures recorded by Windows Security Auditing.
* Source address identified as localhost (127.0.0.1).

---

## Evidence Collected

### Screenshots

Store screenshots in:

```text
screenshots/lab-01-failed-logon-investigation/
```

Files:

```text
failed_logon_events.png
failed_logon_event_details.png
```

---

## Investigation Findings

### Event ID

```text
4625
```

### Logon Type

```text
2
```

Interactive logon at the local workstation.

### Source Address

```text
127.0.0.1
```

Indicates the authentication attempt originated from the local machine.

### Process

```text
C:\Windows\System32\svchost.exe
```

Windows service process responsible for the authentication request.

### Conclusion

Review of the event data indicated that the failed logon attempts were generated during a controlled lab exercise involving intentionally incorrect password entries. No indicators of malicious activity were identified.

---

## Security Relevance

Failed authentication events are frequently investigated by:

* SOC Analysts
* Incident Responders
* Security Engineers
* Threat Hunters

Common use cases include:

* Brute-force detection
* Password spraying investigations
* Account lockout investigations
* Unauthorized access monitoring
* Insider threat investigations

---

## Key Takeaways

* Windows records failed authentication attempts using Event ID 4625.
* Event Viewer provides detailed authentication metadata.
* Logon Type helps determine how authentication occurred.
* Security analysts use authentication logs to identify suspicious activity.
* Understanding authentication events is foundational to SOC investigations.

---

## Note

This lab was performed in a personal lab environment for educational and portfolio development purposes.
