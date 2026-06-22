## What I Observed

PowerShell was used to review active processes running on the workstation.

The process list displayed:

* Process Name
* Process ID (PID)
* CPU Usage
* Working Set Memory
* Handle Count

The output provided visibility into applications actively consuming system resources.

---

## Evidence Collected

### Screenshots

Store screenshots in:

```text
screenshots/lab-05-process-investigation/
```

Files:

```text
process_list.png
process_investigation.png
```

---

## Investigation Findings

### Process Enumeration

The following command was used to identify the top CPU-consuming processes:

```powershell
Get-Process | Sort-Object CPU -Descending | Select-Object -First 15
```

Several applications appeared among the highest resource consumers, including:

```text
Spotify
Chrome
Explorer
msedgewebview2
OneDrive
```

### Resource Utilization Review

The process consuming the most cumulative CPU time during the review was:

```text
Spotify
CPU Time: 511.47 seconds
```

Multiple Chrome browser processes were also observed, which is expected because modern browsers use separate processes for tabs, extensions, and rendering components.

### Individual Process Investigation

The Canva process was selected for further review.

Command executed:

```powershell
Get-Process Canva
```

Observed results:

```text
Process Name: Canva

PID 21080
CPU Time: 0.09 seconds

PID 21640
CPU Time: 0.36 seconds
```

Two Canva processes were running simultaneously, which is common for modern desktop applications that utilize multiple background components.

### Security Analysis

The reviewed processes appeared consistent with normal workstation activity.

Examples included:

```text
Spotify
Chrome
Canva
Explorer
OneDrive
```

No unusual process names, excessive resource consumption, or suspicious executable names were identified during this review.

### Conclusion

PowerShell successfully enumerated running processes and provided visibility into resource utilization. Reviewing active processes demonstrated how analysts identify running applications, investigate process behavior, and establish a baseline of normal system activity.
