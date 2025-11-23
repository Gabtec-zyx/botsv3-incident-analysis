# **BOTSv3 Incident Analysis – Splunk Forensics Investigation**  
COMP5002 – Security Operations & Incident Management  
University of Plymouth  

---

## **1. Introduction**  
This repository documents a full security investigation of the **Boss of the SOC v3 (BOTSv3)** dataset using **Splunk Enterprise**. BOTSv3 simulates a realistic cyberattack on a fictional brewing company, *Frothly*, containing rich log data across:

- Email systems  
- OneDrive & Office 365  
- Endpoint logs (Windows + Linux)  
- Network telemetry  
- Azure & AWS cloud services  

The goals of this investigation are to:

- Deploy and configure Splunk on Ubuntu  
- Ingest and validate BOTSv3 logs  
- Perform advanced SPL searches to uncover malicious activity  
- Answer all 300-level forensics questions  
- Produce a professional SOC-style incident report and video presentation  

This repository also demonstrates continuous improvement with commits over multiple weeks, reflecting real SOC workflows and version control practices.

---

## **2. SOC Roles & Incident Handling Reflection**  

Modern SOC operations consist of several layers:

| SOC Tier | Responsibilities |
|---------|------------------|
| **Tier 1:** Entry-level analysts | Initial alert triage, false-positive reduction |
| **Tier 2:** Incident responders | Deep log investigation, kill chain mapping |
| **Tier 3:** Threat hunters | Malware analysis, adversary behaviour detection |
| **IR / DFIR Team** | Containment, eradication, recovery |

The BOTSv3 dataset presents events across the entire **incident lifecycle**, from initial phishing delivery to lateral movement and persistence, allowing full application of SOC practices.

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

## **4. BOTSv3 Guided Questions (300-Level Forensics)**  

This section will include:

- SPL queries  
- Screenshots of outputs  
- Analysis of attacker behaviour  
- SOC relevance  

*(To be completed after Splunk analysis.)*

---

## **5. Conclusion**  

This project demonstrates hands-on SOC analysis, applying Splunk SPL searches, endpoint forensics, and email/cloud telemetry correlation. BOTSv3 provides a realistic SOC environment for practicing incident handling and threat investigation.

---

## **6. References (IEEE)**  
*(To be added when final report is complete.)*

---

## **7. Video Presentation**  
A link to the 10-minute walkthrough on YouTube will be added here.

---

## **8. AI Use Declaration**  

This project falls under the **Partnered Work** AI category, as per COMP5002 guidelines.  
The full declaration is stored in:

```
/ai-declaration/generative-ai-usage.md
```

