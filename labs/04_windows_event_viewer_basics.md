## What I Observed

Windows Event Viewer organizes logs into several categories that help administrators and security analysts monitor system activity.

The primary Windows log categories reviewed included:

* Application
* Security
* Setup
* System
* Forwarded Events

Each category contains records of specific operating system, application, and security-related events.

Reviewing individual events revealed detailed metadata including Event ID, Source, Timestamp, Event Level, User Context, and Event Description.

---

## Evidence Collected

### Screenshots

Store screenshots in:

```text
screenshots/lab-04-event-viewer-basics/
```

Files:

```text
event_viewer_overview.png
event_details_review.png
```

---

## Investigation Findings

### Event Viewer Navigation

Reviewed the primary Windows logging categories:

```text
Application
Security
Setup
System
Forwarded Events
```

These categories provide visibility into operating system activity, application behavior, and security-related events.

### Event Metadata Review

A System log event was examined to review event structure and metadata.

Observed fields included:

```text
Event ID: 16
Source: Kernel-General
Level: Information
User: SYSTEM
Computer: Angie_PC
```

### Event Description

The reviewed event recorded an update to a Windows application settings file.

The event description indicated that access history information within a Windows Photos application settings file had been updated.

### Security Analysis

This event represented normal operating system activity and did not indicate malicious behavior.

Reviewing event metadata allows analysts to determine:

* What occurred
* When it occurred
* Which component generated the event
* Which user or system account was involved

### Conclusion

Windows Event Viewer provides centralized visibility into system activity and allows analysts to review detailed event information. The reviewed System event demonstrated how Windows records operating system activity and provides metadata that can assist during investigations and troubleshooting.
