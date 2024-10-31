# Incident and Investigation Response

This repository documents my hands-on experiences in **Incident Response and Investigation** on the [LetsDefend](https://letsdefend.io/) platform. Each incident is thoroughly investigated following industry-standard playbooks and categorized based on alert severity: **Critical**, **High**, and **Medium**. Each alert will be documented with an in-depth walkthrough to assess whether it is a **True Positive (TP)** or **False Positive (FP)**.

---
## 📊 Dashboard Overview

| 🔢 **S.No** | 🛡️ **Severity** | 📅 **Date**    | 🔍 **Rule Name**                  | 📄 **Event ID** | 📝 **Type**       | 🔗 **Walkthrough Link**       |
|-------------|----------------|---------------|-----------------------------------|----------------|------------------|-------------------------------|
| 1️⃣         | ![Medium](https://img.shields.io/badge/Medium-yellow) | Oct, 24, 2024, 05:57 AM  | Phishing Alert - Deceptive Mail Detected | 257       | Exchange         | [View Walkthrough](https://github.com/maheavula/Incident-Investigation-Response/blob/main/Medium/SOC282%20-%20Phishing%20Alert%20-%20Deceptive%20Mail%20Detected.md) |  
| 2️⃣         | ![High](https://img.shields.io/badge/High-red)     | 2024-10-27, 04:05 AM | SOC104 - Malware Detected | 36             | Malware          | [View Walkthrough](https://github.com/maheavula/Incident-Investigation-Response/blob/main/High/SOC104%20-%20Malware%20Detected.md) |  
| 3️⃣         | ![Critical](https://img.shields.io/badge/Critical-darkred) | Oct, 27, 2024, 08:55 AM | ⭐ SOC274 - Palo Alto Networks PAN-OS Command Injection Vulnerability Exploitation (CVE-2024-3400) | 249 | Web Attack      | [View Walkthrough](https://github.com/maheavula/Incident-Investigation-Response/tree/main/Critical) |  
| 4️⃣         | ![Critical](https://img.shields.io/badge/Critical-darkred) | Oct, 28, 2024, 03:13 PM | ⭐ SOC227 - Microsoft SharePoint Server Elevation of Privilege - Possible CVE-2023-29357 Exploitation | 189 | Web Attack      | [View Walkthrough](https://github.com/maheavula/Incident-Investigation-Response/blob/main/Critical/SOC227%20-%20Microsoft%20SharePoint%20Server%20Elevation%20of%20Privilege%20-%20Possible%20CVE-2023-29357%20Exploitation.md) |  
| 5️⃣         | ![Medium](https://img.shields.io/badge/Medium-yellow) | Oct, 28, 2024, 06:58 PM  | SOC176 - RDP Brute Force Detected | 234       | Brute Force      | [View Walkthrough](https://github.com/maheavula/Incident-Investigation-Response/blob/main/Medium/SOC176%20-%20RDP%20Brute%20Force%20Detected.md) |  
| 6️⃣         | ![High](https://img.shields.io/badge/High-red) | Oct, 29, 2024, 05:00 AM  | SOC202 - FakeGPT Malicious Chrome Extension | 153       | Data Leakage    | [View Walkthrough](https://github.com/maheavula/Incident-Investigation-Response/blob/main/High/SOC202%20-%20FakeGPT%20Malicious%20Chrome%20Extension.md) |  
| 7️⃣         | ![Medium](https://img.shields.io/badge/Medium-yellow) | Oct, 29, 2024, 08:27 AM  | SOC251 - Quishing Detected (QR Code Phishing) | 214       | Exchange         | [View Walkthrough](https://github.com/maheavula/Incident-Investigation-Response/blob/main/Medium/SOC251%20-%20Quishing%20Detected%20(QR%20Code%20Phishing).md) |  
| 8️⃣         | ![Medium](https://img.shields.io/badge/Medium-yellow) | Oct, 31, 2024, 06:56 AM  | ⭐ SOC173 - Follina 0-Day Detected | 123       | Malware          | [View Walkthrough](https://github.com/maheavula/Incident-Investigation-Response/blob/main/Medium/SOC173%20-%20Follina%200-Day%20Detected.md) |  


---


## Repository Structure

```plaintext
incident-and-investigation/
├── Critical/
│   
├── High/
│  
├── Medium/
│ 
└── README.md
```
## Repository Structure

- **Critical**: Documents incidents with severe impact (e.g., malware, data breaches, phishing attacks).  
- **High**: Alerts that indicate major issues but do not pose an immediate threat (e.g., network scanning, C2 communications).  
- **Medium**: Alerts that require monitoring but do not indicate immediate compromise (e.g., failed logins, minor anomalies).

---

## How to Use This Repository

- **Browse incidents**: Navigate to folders by alert severity. Each alert is documented with detailed insights on how the investigation was carried out.
- **Learning objectives**: Each walkthrough is intended to demonstrate how to apply security principles to real-world scenarios using structured analysis.



---

### **Tips for Writing Effective Walkthroughs**

1. **Be Concise, Yet Detailed**: Avoid jargon or unnecessary complexity. Ensure your findings and steps are clear and understandable.  
2. **Link Tools and Resources**: Provide links to tools like VirusTotal, Shodan, etc., when mentioning them.  
3. **Use Screenshots (if allowed)**: Adding screenshots (e.g., from dashboards or SIEM tools) can help illustrate key points.  
4. **Document the Timeline**: When possible, note timestamps of key events to align with your findings.  
5. **Highlight Challenges and Solutions**: If you encounter difficulties, document how you overcame them.

---


With this structure, you’ll be able to create a professional repository that showcases your incident response skills. Over time, this portfolio will not only demonstrate your expertise but also reflect your growth in handling different types of alerts.

