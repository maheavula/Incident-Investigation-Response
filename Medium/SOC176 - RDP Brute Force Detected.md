# SOC176 - RDP Brute Force Detected  

## Overview  

![Overview](https://github.com/user-attachments/assets/15cef05b-1824-426d-a651-d46ed2dd48cf)  

This report investigates the **SOC176 - RDP Brute Force Detected** alert. The security system flagged multiple **unauthorized RDP login attempts** from an external source, indicating a possible brute force attack. The goal of this investigation is to confirm the attack and mitigate its impact.  

---

## Investigation Steps  

### 1. **Taking Ownership and Creating a Case**  
Start by **taking ownership** of the alert. Next, **create a case** by clicking the **"Create Case"** button, which redirects you to the **Case Management** page to initiate the investigation.  

![Create Case](https://github.com/user-attachments/assets/31d455a3-209a-4063-97f6-b3bcd8fc6095)  

Click **"Start Playbook"** to begin the investigation.  

![Incident Details](https://github.com/user-attachments/assets/4e53f1ee-325e-411f-bcc6-18e36bbbe2c7)  

---

### 2. **Determining Source Context**  
The first step is to determine if the **source IP address** is **external or internal**. As the IP address is from an **external source**, select **"External"**.  

![Context](https://github.com/user-attachments/assets/c9539205-2ffd-4e69-87fc-1f378d3c4aac)  

---

### 3. **Reputation Check of Source IP Address**  
Perform a **reputation check** for the source IP address using various threat intelligence platforms:  
- **LetsDefend**: Flagged the IP as **malicious**.  
![Threat Intel](https://github.com/user-attachments/assets/f1e282e1-c7aa-49b0-99d9-f95b60a491b7)  

- **VirusTotal**: 14 vendors identified the IP as **malicious**.  
![VirusTotal](https://github.com/user-attachments/assets/b5ded556-79ac-4e02-a44f-37eae0089817)  

- **AbuseIPDB**: Reported that the IP has been found over **400,000 times** in its database with a **100% abuse rating**.  
![AbuseIPDB](https://github.com/user-attachments/assets/aa392d71-ee84-4670-a769-10ae1da6e832)  

Select **"Yes"** to confirm that the IP address is suspicious.  

---

### 4. **Traffic Analysis for RDP Brute Force Attempts**  
Review **log management** for evidence of the attacker's activity on **RDP protocol**.  

![Traffic Analysis](https://github.com/user-attachments/assets/f9f7fd52-7f7c-4704-9df3-3f769c7cdf65)  

Logs indicate that multiple **RDP login attempts** were made using different **usernames and passwords**. Eventually, one attempt was **successful**, granting the attacker access to the system.  

---

### 5. **Scope of the Attack**  
Determine if the attacker attempted to access **multiple systems**. In this case, the **attacker only targeted a single system**. Therefore, select **"No"**.  

![Determine Scope](https://github.com/user-attachments/assets/aa5563f1-bfb0-42da-a5d8-cae87daf3968)  

---

### 6. **Confirming Successful Login**  
The logs show that the **RDP brute force attack** resulted in a **successful login** with **Event ID 4624**.  

![Log Management](https://github.com/user-attachments/assets/1cca3e9c-92b7-49ea-aa33-9b46596904bd)  

Select **"Yes"** to confirm the successful login.  

---

### 7. **Isolating the Affected System**  
Since the attack was successful, it is necessary to **isolate the system** to prevent further data exposure.  

![Isolated](https://github.com/user-attachments/assets/173ee49a-0034-4af8-a06d-d940257c74f3)  

Perform **containment** through **endpoint security** to restrict access and mitigate the impact.  

![Containment](https://github.com/user-attachments/assets/8f3ec9f3-9d47-4857-b65d-2a4fd477c7c0)  

---

### 8. **Post-Incident Lessons Learned**  
Document the following **post-incident lessons learned**:  
- **How did the attack occur?**  
- **How well did staff and management respond?**  
- **What changes should be made to prevent future incidents?**  
- **What indicators should be monitored going forward?**  

Enter relevant **artifacts**, including **source IP** and **destination IP**, into the system.  

---

### 9. **Analysis Note**  
**Analysis Summary**:  
- The **RDP brute force attack** was confirmed to be **successful**.  
- The attacker made multiple login attempts before finally gaining access.  
- The affected system has been **contained** to prevent further data exposure.  

![Finish Playbook](https://github.com/user-attachments/assets/c52f6cdf-7d68-4282-ab2f-51e786347436)  

---

### 10. **Completing the Playbook and Closing the Alert**  
Click **"Finish Playbook"** to conclude the investigation process.  

![Close Alert](https://github.com/user-attachments/assets/bf9ac198-28df-4554-96b5-3797b2855ce2)  

Select **"True Positive"** and enter a **note** confirming that the alert was valid. Finally, close the alert.  

---

## Conclusion  

This investigation confirms that the **SOC176 - RDP Brute Force Detected** alert is a **true positive**. The attacker successfully gained access through **RDP protocol** using brute force. The affected system was **contained** to prevent further compromise, and post-incident actions were documented to improve future response.  

Stay vigilant and continue monitoring for similar activity.  
