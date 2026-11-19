# Hardening Windows Security Logging

**Skills:** Windows 10 · Advanced Audit Policy · virtualization · endpoint visibility

## Goal
By default, Windows doesn't record many of the events a SOC analyst needs for an investigation. In this lab I built a Windows 10 virtual machine and turned on advanced security logging so logons and other security events get recorded.

## 1. Build the lab machine
I installed Windows 10 in Oracle VirtualBox and renamed the computer to `pc-sec` so it's easy to identify in logs.

<img width="1017" height="759" alt="Renaming the PC to pc-sec" src="https://github.com/user-attachments/assets/4daf1046-5005-47b5-95ef-126aef2058ae" />

## 2. Enable advanced audit policies
I turned on the advanced audit policy settings in the Windows security policy editor.

<img width="1021" height="766" alt="Advanced audit policy settings" src="https://github.com/user-attachments/assets/44fa350e-320b-43ff-911a-3a4712b6774f" />
<img width="1014" height="763" alt="Audit policy configuration" src="https://github.com/user-attachments/assets/43d4ee48-530c-408b-b390-1ba17878c604" />
<img width="1017" height="771" alt="Audit policy configuration, continued" src="https://github.com/user-attachments/assets/b8491699-8638-4aed-a585-4f01ba8a9821" />

## Why it matters
With these policies on, Windows writes security events to the Event Log, for example **4624** (successful logon), **4625** (failed logon) and **4688** (new process created). A SIEM like Splunk ([see Project 1](./01-splunk-brute-force-detection.md)) can then collect those events and alert on them.

## What I learned
- The difference between basic and advanced audit policies in Windows
- Which events matter most for detecting suspicious logons
- How a lab VM gives you a safe place to test security settings
