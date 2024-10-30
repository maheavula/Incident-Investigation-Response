# SOC202 - FakeGPT Malicious Chrome Extension  

## Overview  

![Overview](https://github.com/user-attachments/assets/3397bca7-cf11-4d50-9a90-98276290ecad)  

This report addresses the **SOC202 - FakeGPT Malicious Chrome Extension** alert, classified as **High severity**. The purpose of this investigation is to determine the nature of the threat and mitigate potential risks.  

---

## Investigation Steps  

### 1. **Taking Ownership and Creating a Case**  
Start the process by **taking ownership** of the alert. Then, click **"Create Case"** on the investigation page to begin the case management process.  

![Create Case](https://github.com/user-attachments/assets/a26e43bc-fc39-432a-a77b-7578cf884c08)  

---

### 2. **Starting the Playbook**  
Once the case is created, click **"Start Playbook"** from the **Case Management** page to begin the investigation.  

![Threat Indicator](https://github.com/user-attachments/assets/3554426a-0e01-46cb-abb7-36234ab0c829)  

---

### 3. **Defining the Threat Indicator**  
The playbook requires defining the **threat indicator** as **incoming**, **outgoing**, or **other**. Since the specific category isn’t listed, select **"Other"**.  

![Threat Indicator](https://github.com/user-attachments/assets/bca1c84f-91fd-498c-a5c1-5bda647bec02)  

---

### 4. **Checking Device Quarantine Status**  
Review the **endpoint security** to determine if the device is quarantined. As the device is **not quarantined**, select **"Not Quarantined"**.  

---

### 5. **Analyzing the Extension File**  
Analyze the suspicious extension file using online sandbox tools to determine its behavior:  

- **VirusTotal**: No vendors flagged the extension as malicious.  
![VirusTotal](https://github.com/user-attachments/assets/9f95d27a-da4f-44ca-9421-33ab7da1b71d)  

- **Hybrid Analysis**: Declared the extension **clean**, with no signs of malicious behavior.  
![Hybrid Analysis](https://github.com/user-attachments/assets/c5a7bee7-735f-4235-8003-44f83721d332)  

- **ANY.RUN**: Confirmed **no threat detected**.  

---

### 6. **Investigating Logs for Malicious Behavior**  
Although sandbox analysis shows the extension as **clean**, **log management** reveals HTTP requests from the host device to two suspicious IP addresses:  
- **18.140.6.45**  
- **52.76.101.124**  

![Raw Logs](https://github.com/user-attachments/assets/6f36678c-a0e9-4df9-9b16-6b62976da678)  
![Raw Log](https://github.com/user-attachments/assets/d8a89dde-489b-4244-860b-ad6ea5100624)  

These requests are suspicious because the domain differs from the legitimate **ChatGPT** domain. This indicates **malicious behavior**.  

---

### 7. **Confirming C2 Access**  
Further log analysis confirms that the host device accessed a **Command-and-Control (C2)** address. Both browser history and logs show evidence of interaction with the malicious domain. Select **"Accessed"** to confirm this behavior.  

![Accessed](https://github.com/user-attachments/assets/f206c8b9-d23c-4617-bf4c-ee8e0d8d7852)  

---

### 8. **Containing the Host Device**  
To prevent further compromise, the host device must be **contained**. Use **endpoint security** tools to isolate the device from the network.  

![Containment](https://github.com/user-attachments/assets/5903bb6e-5c22-4d22-83c3-1c1de3df7370)  
![Host Contain](https://github.com/user-attachments/assets/7e1ae74c-dce9-4317-824e-3397a6113b85)  

---

### 9. **Entering Artifacts**  
Document the **Indicators of Compromise (IOCs)**, including **source and destination IP addresses**, in the designated fields.  

![Add Artifacts](https://github.com/user-attachments/assets/26c69ec5-2048-4ccd-9f1c-78f468f0e8c0)  

---

### 10. **Writing the Analysis Note**  
**Analysis Summary**:  
- **Malicious Extension Identified**: The investigation confirmed that the **FakeGPT extension** is **malicious**.  
- The host device was contained to prevent **further spread** of the threat.  
- This is a **true positive** alert, triggered correctly by the security system.  

---

### 11. **Completing the Investigation and Closing the Alert**  
Click **"Confirm"** to save all investigation data and finalize the playbook.  

![Confirm](https://github.com/user-attachments/assets/4fafdc8f-8d08-493f-a572-e8b0634f4ae5)  

Finally, click **"Close Alert"** and select **"True Positive"** to conclude the investigation.  

![Close Alert](https://github.com/user-attachments/assets/6ba8f942-fa70-4f6a-836d-f41fec47e4dd)  

---

## Conclusion  

This investigation confirms that the **SOC202 - FakeGPT Malicious Chrome Extension** alert is a **true positive**. The extension was identified as a **malicious file**, and the host device was successfully **contained** to prevent further compromise.  

Continue monitoring for any related threats and ensure that staff remain alert to similar malicious extensions.
