# **BOTSv3 Incident Analysis – Splunk Forensics Investigation**  
COMP5002 – Security Operations & Incident Management  
University of Plymouth  

---



## **1. Introduction**  
This repository documents a full security investigation of the Boss of the SOC v3 (BOTSv3) dataset using Splunk Enterprise. BOTSv3 simulates a realistic cyberattack against a fictional brewing company, Frothly, and provides rich, multi-source telemetry, including:

- Email and SMTP logs

- Microsoft 365 and OneDrive activity

- Windows endpoint telemetry (Sysmon, Security logs)

- Linux endpoint telemetry (Osquery)

- Network and authentication activity

- Cloud service logs (Azure and AWS)

The purpose of this investigation is to replicate a real-world Security Operations Centre (SOC) workflow by deploying Splunk, analysing malicious activity, and reconstructing the attacker’s actions across the incident lifecycle.

The objectives of this project are to:

- Install and configure Splunk Enterprise on an Ubuntu virtual machine

- Ingest and validate the BOTSv3 dataset

- Perform advanced SPL-based forensic analysis

- Answer all BOTSv3 investigation questions

- Correlate activity across cloud, email, endpoint, and Linux systems

- Produce a professional SOC-style incident report and video presentation

---

## **2. SOC Roles & Incident Handling Reflection**  

Security Operations Centres operate using tiered analyst roles, each responsible for different stages of incident handling:

| SOC Tier | Responsibilities |
|---------|------------------|
| **Tier 1:** Entry-level analysts | Initial alert triage, false-positive reduction |
| **Tier 2:** Incident responders | Deep log investigation, kill chain mapping |
| **Tier 3:** Threat hunters | Malware analysis, adversary behaviour detection |
| **IR / DFIR Team** | Containment, eradication, recovery |

The BOTSv3 dataset spans the full incident lifecycle, from initial phishing delivery through malware execution, privilege escalation, persistence, and lateral movement.
Our investigation reflects how SOC tiers collaborate by escalating validated findings, correlating logs across platforms, and producing evidence-driven conclusions.

---

## **3. Installation & Data Preparation**  

### **3.1 Splunk Installation (Ubuntu 22.04)**

```bash
wget -O splunk-9.deb 'https://download.splunk.com/products/splunk/releases/9.1.0/linux/splunk-9.1.0-linux-2.6-amd64.deb'
sudo dpkg -i splunk-9.deb
sudo /opt/splunk/bin/splunk start --accept-license
```

---

### **3.2 BOTSv3 Dataset Ingestion**

Dataset:  
https://github.com/splunk/botsv3  

Add data using Splunk UI:

**Add Data → Upload → botsv3_data_set.tgz → Index = botsv3**

Evidence screenshots stored in:

```
/evidence/botsv3-ingestion/
```

---

## **4. BOTSv3 Guided Questions**  

This section documents the investigation of all BOTSv3 300-level questions.
For each question, the following are provided:

- Analytical thought process

- Relevant SPL queries

- Screenshots and extracted artefacts

- Final answer

- SOC relevance

The analysis covers:

- Malicious OneDrive uploads

- Macro-enabled email attachments

- Embedded executable execution

- Linux account creation and credential abuse

- Windows privilege escalation

- Backdoor processes listening on leet ports

- Malware hash identification

---

## **5. Conclusion**  

This investigation demonstrates how effective SIEM-based log correlation can uncover a complete intrusion chain. Key weaknesses identified include insufficient email filtering, weak endpoint hardening, and limited behavioural monitoring.

The exercise reinforces the importance of:

- Multi-source log visibility

- Structured SOC escalation paths

- Proactive threat hunting

- Evidence-driven incident response

BOTSv3 provides a realistic environment for developing professional SOC investigation skills.

---

## **6. References (IEEE)**  
All academic and industry references are provided in IEEE format in the accompanying PDF report.

---

## **7. Video Presentation**  
A 10-minute walkthrough demonstrating Splunk queries, investigative methodology, and SOC findings linked in botsv3-incident-analysis/video/presentation.md.

---

## **8. AI Use Declaration**  

This project follows the Partnered Work AI category in accordance with COMP5002 guidelines.
AI tools were used for research assistance and language refinement only.
The full declaration is available at:
/ai-declaration/generative-ai-usage.md


