# 02 — Account Lockout Analysis

## Goal

Understand how Windows account lockout policies help protect systems from repeated authentication failures and learn how security analysts investigate account lockout scenarios.

Account lockout policies are commonly reviewed during authentication investigations to determine how many failed login attempts are permitted before an account is temporarily restricted.

---

## What I Did

* Reviewed local Windows account policies using PowerShell.
* Examined account lockout configuration settings.
* Identified the lockout threshold, duration, and observation window.
* Generated repeated failed authentication attempts.
* Observed Windows protective mechanisms during authentication testing.
* Documented findings and security implications.

---

## Tools Used

### PowerShell

Used to review local account policies.

### Command Used

```powershell
net accounts
```

Displays password and account lockout policy settings configured on the local workstation.

---

## What I Observed

The system was configured with the following account lockout settings:

### Lockout Threshold

```text
10 failed attempts
```

### Lockout Duration

```text
10 minutes
```

### Lockout Observation Window

```text
10 minutes
```

During testing, repeated failed authentication attempts triggered additional Windows verification requirements and restart prompts before a full account lockout event could be generated.

These protections are designed to slow repeated authentication attempts and reduce the effectiveness of brute-force activity.

---

## Evidence Collected

### Screenshots

Store screenshots in:

```text
screenshots/lab-02-account-lockout-analysis/
```

Files:

```text
account_policy_review.png
```

---

## Investigation Findings

### Authentication Controls Identified

The workstation was configured to temporarily lock an account after ten failed authentication attempts within a ten-minute observation window.

### Windows Protective Behavior

During testing, Windows introduced additional verification challenges and restart requirements after multiple failed sign-in attempts.

### Security Impact

These controls help protect user accounts by:

* Limiting repeated authentication attempts.
* Slowing brute-force attacks.
* Reducing unauthorized access opportunities.
* Encouraging investigation of repeated authentication failures.

### Conclusion

Review of the account policy confirmed that the system enforces account lockout protections after repeated authentication failures. Testing demonstrated additional Windows security controls that increase resistance to repeated sign-in attempts. No malicious activity was identified; all authentication failures were generated during a controlled lab exercise.

---

## Security Relevance

Account lockout investigations are frequently performed by:

* SOC Analysts
* Security Engineers
* Identity and Access Management Teams
* Help Desk Analysts
* Incident Responders

Common use cases include:

* Account lockout investigations
* Password spraying investigations
* Brute-force attack detection
* Authentication troubleshooting
* User access reviews

---

## Key Takeaways

* Windows account lockout policies help protect against repeated authentication failures.
* Lockout thresholds determine how many failed attempts are permitted before restrictions are applied.
* Observation windows define the timeframe used when counting failed attempts.
* Security analysts regularly review account policies during authentication investigations.
* Understanding authentication controls is foundational for SOC and incident response work.

---

## Note

This lab was performed in a personal lab environment for educational and portfolio development purposes.

