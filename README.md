# Incident and Investigation Response

This repository documents my hands-on experiences in **Incident Response and Investigation** on the [LetsDefend](https://letsdefend.io/) platform. Each incident is thoroughly investigated following industry-standard playbooks and categorized based on alert severity: **Critical**, **High**, and **Medium**. Each alert will be documented with an in-depth walkthrough to assess whether it is a **True Positive (TP)** or **False Positive (FP)**.

---
## 📊 Dashboard Overview

| 🔢 **S.No** | 🛡️ **Severity** | 📅 **Date**    | 🔍 **Rule Name**                  | 📄 **Event ID** | 📝 **Type**       | 🔗 **Walkthrough Link**       |
|-------------|----------------|---------------|-----------------------------------|----------------|------------------|-------------------------------|
| 1️⃣         | ![Medium](https://img.shields.io/badge/Medium-yellow) | Oct, 24, 2024, 05:57 AM  | Phishing Alert - Deceptive Mail Detected | 257       | Exchange         | [View Walkthrough](https://github.com/maheavula/Incident-Investigation-Response/blob/main/Medium/SOC282%20-%20Phishing%20Alert%20-%20Deceptive%20Mail%20Detected.md) |  
| 2️⃣         | ![High](https://img.shields.io/badge/High-red)     | 2024-10-27, 04:05 AM | SOC104 - Malware Detected | 36             | Malware          | [View Walkthrough](https://github.com/maheavula/Incident-Investigation-Response/blob/main/High/SOC104%20-%20Malware%20Detected.md) |  


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

