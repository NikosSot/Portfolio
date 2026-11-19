# Detecting Brute-Force Login Attempts with Splunk

**Skills:** SIEM setup · log ingestion · Python · brute-force detection

## Goal
Brute-force attacks show up as many failed logins against one account or from one source in a short time. In this lab I built a small SIEM setup, fed it authentication logs and used it to find that pattern.

## 1. Set up Splunk
I installed Splunk Enterprise and added the **Splunk Security Essentials** app, which comes with ready-made security detections.

<img width="1899" height="922" alt="Splunk home screen" src="https://github.com/user-attachments/assets/3a767486-26a9-427e-b52c-d5ba0fa30524" />
<img width="1872" height="871" alt="Splunk Security Essentials app" src="https://github.com/user-attachments/assets/631ccff2-256a-4275-8708-46a3df0c7d4e" />

## 2. Generate test login data with Python
I had no real attack traffic, so I wrote a Python script that produces authentication log entries, including a burst of failed logins that looks like a brute-force attempt.

<img width="1045" height="934" alt="Python script that generates login data" src="https://github.com/user-attachments/assets/123cbd06-179b-48e2-9dce-d45a50e60d6a" />

Output of the script:

<img width="986" height="997" alt="Generated log output" src="https://github.com/user-attachments/assets/537bcd70-bc6c-44f0-804a-ad4829e8bd28" />

## 3. Ingest the logs into Splunk
I uploaded the generated file into Splunk so the events could be searched.

<img width="1915" height="927" alt="Log data added to Splunk" src="https://github.com/user-attachments/assets/a30e048d-266f-4298-b033-a31916b73849" />

## What I learned
- How a SIEM takes in raw log data and makes it searchable
- Why test data helps when you're building and checking a detection
- What a brute-force pattern looks like in authentication logs
