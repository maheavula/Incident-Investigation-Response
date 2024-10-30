# SOC251 - Quishing Detected (QR Code Phishing)  

## Overview  

![Overview](https://github.com/user-attachments/assets/c8140446-4424-4118-b5cf-f72adf1ff2f9)  

This report covers the **SOC251 - Quishing Detected** alert, which involves **QR code phishing**. The investigation aims to confirm whether the alert is **malicious** and take appropriate actions to mitigate further risks.  

---

## Investigation Steps  

### 1. **Taking Ownership and Creating a Case**  
Begin by **taking ownership** of the alert. From the **investigation page**, click **"Create Case"** to open a case and start the investigation.  

![Create Case](https://github.com/user-attachments/assets/303ef3d2-6d0d-42bd-b1a4-bb93b81b19f2)  

---

### 2. **Starting the Playbook**  
Click **"Start Playbook"** to proceed with the investigation using the guided steps.  

![Incident Details](https://github.com/user-attachments/assets/6ad43186-aa97-480a-94c5-afc18b729587)  

---

### 3. **Verifying the Alarm’s Validity**  
Since **Tier 1 escalations** are not always **true positives**, it is essential to verify the malicious activity before proceeding with the **Incident Response** process. Click **Next** to continue.  

---

### 4. **Reconnaissance Identification**  
**Reconnaissance** is a key phase where attackers gather information about their targets. The goal of this playbook is to identify **potential reconnaissance activities**.  

---

### 5. **Log Analysis**  
A **suspicious SMTP exchange** was found from the IP address **158.69.201.47**, with the following email header details:  

- **Sender Email**: security@microsecmfa.com  
- **Destination Email**: Claire@letsdefend.io  
- **Subject**: New Year's Mandatory Security Update: Implementing Multi-Factor Authentication (MFA)  

![Raw Log](https://github.com/user-attachments/assets/9702ab20-118f-4590-860b-39317d8b8e3c)  

---

### 6. **Email Security Analysis**  
The **sender’s domain** is **not a legitimate Microsoft domain**, which makes it suspicious. The message included a **QR code phishing** attempt.  

![QR Code](https://github.com/user-attachments/assets/385f3966-bc8f-4a9d-8692-550b1d52b68c)  

---

### 7. **Identifying the Attack Type**  
Based on the analysis, the attack is identified as **Phishing for Information**.  

![Reconnaissance](https://github.com/user-attachments/assets/a1e0a72e-0434-4bf1-a088-4327edc8440d)  

---

### 8. **Determining Attacker IP Origin**  
The **attacker’s IP** is **external**, as it belongs to a **public IP range**.  

![Attacker IP Analysis](https://github.com/user-attachments/assets/72d205e7-6b8a-459f-b63b-556c6ba900c3)  

---

### 9. **Checking IP Reputation**  
Perform a **reputation check** on the attacker’s IP:  
- **LetsDefend Threat Intel**: Categorized as **phishing**.  
![Threat Intel](https://github.com/user-attachments/assets/04859967-88cb-457e-849e-854cadbeaeee)  

- **VirusTotal**: 12 vendors flagged it as **malicious**.  
![VirusTotal](https://github.com/user-attachments/assets/6dfca777-a093-47fb-a924-66c02e3ab48b)  

- **AbuseIPDB**: Although the confidence level is low, the IP was found **340 times** in the database.  

---

### 10. **Determining Scope of the Attack**  
Only **one device** was affected by the phishing attack. Therefore, select **No** to confirm that there are no additional affected devices.  

---

### 11. **Containing the Device**  
To prevent further exposure, **isolate the affected device** by using **endpoint security tools**.  

![Containment](https://github.com/user-attachments/assets/1b3af799-ef36-495b-b360-1cf2aabe874b)  

---

### 12. **Lessons Learned**  
Reflect on the following questions to strengthen future response efforts:  
- **How did the attack occur?**  
- **How well did the team respond?**  
- **What could be improved for future incidents?**  
- **What corrective actions are needed to prevent recurrence?**  
- **What indicators should be monitored moving forward?**  

---

### 13. **Adding Artifacts and Finalizing the Investigation**  
Enter relevant **artifacts** such as **IP addresses and domains** identified during the investigation.  

![Add Artifacts](https://github.com/user-attachments/assets/844a6835-913a-4b46-bab6-974014bc6824)  

---

### 14. **Writing the Analysis Note**  
**Analysis Summary**:  
- This was confirmed to be a **QR phishing attack**.  
- The sender’s domain was **not legitimate**, and the **device was isolated** to prevent further compromise.  
- The IP has a **poor reputation** based on threat intelligence checks.  

![Playbook Confirm](https://github.com/user-attachments/assets/993df0a5-b4fb-428c-91dd-6b2be6360dac)  

---

### 15. **Completing the Playbook and Closing the Alert**  
Click **"Confirm"** to save the investigation details.  

![Close Alert](https://github.com/user-attachments/assets/0c308d1e-d549-4d90-b1ab-32b4315a0e72)  

---

## Conclusion  

This investigation confirms that the **SOC251 - Quishing Detected** alert is a **true positive**. The phishing attempt was conducted through a **malicious QR code** embedded in a deceptive email. The affected device was **contained**, and all findings have been documented. Continue monitoring for similar phishing campaigns in the future.  
