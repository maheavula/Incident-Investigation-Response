# SOC173 - Follina 0-Day Detected  

## Overview  

![Overview](https://github.com/user-attachments/assets/38b48952-98e0-42d9-97ba-e2f39f0c2bd8)  

This report covers the **SOC173 - Follina 0-Day Detected** alert, which flagged a **zero-day vulnerability** in Microsoft Office. This high-priority investigation will confirm the threat and take necessary containment steps.  

---

## Investigation Steps  

### 1. **Taking Ownership and Creating a Case**  
Start by **taking ownership** of the alert, and then from the **investigation channel**, click **"Create Case"** to initiate the case management process.  

![Create Case](https://github.com/user-attachments/assets/e39a0b03-e7b2-4cec-81f7-eb3d0d43bbc2)  

---

### 2. **Starting the Playbook**  
Upon creation, proceed by clicking **"Start Playbook"** on the **Case Management** page to begin the investigation.  

![Incident Details](https://github.com/user-attachments/assets/f542c099-caca-406f-811a-17cead176ac4)  

---

### 3. **Defining Threat Indicator**  
Define the **threat indicator** by selecting the traffic type. In this case, the alert was triggered after a **.doc file opened and executed an .exe file**, which doesn’t match typical traffic types. Select **"Other"** to proceed.  

![Threat Indicator](https://github.com/user-attachments/assets/ab868c14-63db-47f7-9393-30c0dc355791)  

---

### 4. **Checking for Quarantine Status**  
Review **logs and endpoint security** to confirm if the device is **quarantined**. As the endpoint security reveals that the **device was not quarantined**, select **"Not Quarantined"** to proceed.  

![Quarantine Check](https://github.com/user-attachments/assets/2e6f1775-91ce-42d6-9a57-705d1ee200e1)  

---

### 5. **Analyzing the Malware File**  
Submit the malware **hash** to various analysis tools, which confirmed the file as **malicious**, categorized under **trojan** and **downloader** types.  

- **VirusTotal**: 48 vendors flagged it as **malicious**.  
![VirusTotal](https://github.com/user-attachments/assets/0ae14781-a8c6-4f32-8298-77b3e53e592e)  

- **Hybrid Analysis**: A **threat score of 100/100** and AV detection at 79% confirm it as malicious.  
![Hybrid Analysis](https://github.com/user-attachments/assets/36efc26c-97a4-4889-9af6-cf980e5dad9d)  

- **ANY.RUN**: The analysis scored **100**, further confirming the **malicious nature**.  
![ANY.RUN](https://github.com/user-attachments/assets/d41d158f-f6ce-4f57-9799-f3dd44b7387b)  

---

### 6. **Confirming C2 Access**  
Logs indicate that the device made **requests to suspicious C2 domains**. Both **user logs** and **browser history** confirm that the device **accessed C2**.  

![Requested C2](https://github.com/user-attachments/assets/a1118083-cc58-44eb-a75f-176254c59db8)  
![Accessed C2](https://github.com/user-attachments/assets/95dc52d7-5da9-40b5-aade-f4e271749e6e)  

---

### 7. **Containing the Device**  
To prevent the malware from spreading, **contain the affected device** through endpoint security.  

![Containment](https://github.com/user-attachments/assets/5a0f304d-90bf-43f4-ba83-38fdfdecb89d)  

---

### 8. **Adding Artifacts**  
Document **Indicators of Compromise (IOCs)**, such as **IP addresses and hashes**, collected during the investigation.  

![Add Artifacts](https://github.com/user-attachments/assets/b84ddd3b-0b8e-4370-bf3c-df80297f95d9)  

---

### 9. **Writing the Analysis Note**  
**Analysis Summary**:  
- The file was confirmed as **malicious**, categorized as a **trojan** and **downloader**.  
- It made **C2 requests**, and **48 vendors flagged it** as malware.  
- The device was **contained** to prevent further compromise.  

---

### 10. **Completing the Playbook and Closing the Alert**  
Click **"Confirm"** to save all findings and conclude the investigation.  

![Finish Playbook](https://github.com/user-attachments/assets/4ad86ffc-d684-49c8-ab1b-13bf2ac708cd)  

Finally, mark the alert as a **True Positive** and close the case.  

![Close Alert](https://github.com/user-attachments/assets/78da7fe4-d405-4782-a6aa-8c7a1f9244ff)  

---

## Conclusion  

The **SOC173 - Follina 0-Day Detected** alert is a **true positive**. The document file executed a **malicious payload**, confirmed as a trojan with C2 communication attempts. The device was **contained** to prevent further spread, and findings were thoroughly documented.  

Stay vigilant for similar indicators and strengthen defenses against zero-day threats.  
