#  SOC282 - Phishing Alert - Deceptive Mail Detected Report

![Overview](https://github.com/user-attachments/assets/a4c25b7f-056a-45e8-a6ac-f556366239fc)

## Overview  
A phishing alert, *Deceptive Mail Detected*, was triggered in our system. This attack attempted to target an employee of **LetsDefend**, and despite the detection, the malicious email was allowed by the security device. Below is the step-by-step process followed to investigate and respond to the incident. 

---

## Investigation Process  

1. **Create a Case**  
   Navigate to the **Investigation Channel** and click on the **Create Case** button under the action menu. This action will generate a case with a unique event ID.  
   ![Case Creation](https://github.com/user-attachments/assets/706c6ab2-072d-4355-99f2-b75249a419b9)

2. **Transfer to Case Management**  
   Within seconds, the case is moved to the **Case Management Tab**, where the investigation playbook can be initiated.  
   ![Case Management](https://github.com/user-attachments/assets/3a22f6ef-16ab-45e7-9514-4c58411016a1)

3. **Start Playbook and Collect Details**  
   Upon starting the playbook, a prompt will display the email details. These should be noted for future reference:  
   ![Parse Email](https://github.com/user-attachments/assets/38d0eb65-f9c3-416b-9eb4-bf5ce2343d7f)

   - **Sent Date**: May 13, 2024, 09:22 AM  
   - **SMTP Address**: `103.80.134.63`  
   - **Sender Address**: `free@coffeeshooop.com`  
   - **Recipient Address**: `Felix@letsdefend.io`  
   - **Suspicious Content**: Yes, the email contains spelling errors, unusual fonts, a zipped file, and a suspicious button.  
   - **Attachment**: Yes  

4. **Analyze the File with VirusTotal**  
   The file was analyzed using VirusTotal, with **60 vendors** identifying it as **malicious** and flagging it as a **trojan**.  
   ![VirusTotal](https://github.com/user-attachments/assets/718008b5-e46f-45fc-aaff-8193b748df46)

   After confirming it as malware, select **Malicious** to proceed.  
   ![Malicious Confirmation](https://github.com/user-attachments/assets/3b1fe20b-147c-48a4-a8c5-26b3a26d6f8b)

5. **Check Delivery Status**  
   The next step in the playbook requires checking whether the malicious email was delivered.  
   - The **overview** indicated that the email was allowed through security controls.  

   Confirm the delivery status by selecting **Delivered**.  
   ![Delivery Status](https://github.com/user-attachments/assets/ccbf8599-f480-49b7-a4ba-dfdb731f3b5d)

6. **Delete the Email**  
   Go to the **Email Security Tab**, locate the recipient’s email, and click **Delete** to remove the malicious message from the system.  
   ![Email Deletion](https://github.com/user-attachments/assets/9c35ad18-5ba8-440f-85e4-3fd47a14f71b)

7. **Log Analysis**  
   After analyzing **log management** with the user’s IP address, it was found that within seconds, 4 logs were generated indicating an attempt to access a **Command and Control (C2) server** at `37.120.233.226`.  
   - Since the user clicked on the phishing link, select **Opened**.  
   ![Opened Status](https://github.com/user-attachments/assets/c4398edb-8043-4f76-83cd-211e97a8ea1a)

8. **Contain the Endpoint**  
   To prevent further malicious activities, go to the **Endpoints Tab**, search for the user’s device, and select **Contain and Change** to isolate it from the network.  
   ![Contain Endpoint](https://github.com/user-attachments/assets/e668a9c2-2304-4934-8e04-9dd0a7e176cc)

9. **Add Artifacts to Case**  
   Document all relevant **artifacts** from the alert into the provided fields for reference.  
   ![Add Artifacts](https://github.com/user-attachments/assets/c851ab6d-d469-49df-b67d-1c849d394305)

10. **Document Analysis Notes**  
   Summarize the findings of the investigation in the **Analysis Note** section to ensure accurate documentation of the process.  
   ![Analysis Note](https://github.com/user-attachments/assets/b54d8cc6-3f87-45b1-9ea7-5a72c74ac333)

11. **Finish the Investigation**  
   Click **Confirm** to finalize the investigation process.  
   ![Finish Playbook](https://github.com/user-attachments/assets/3033eef9-bc91-454c-98bb-6d2e3d40d426)

---

## Conclusion  

Finally, go to the **Monitoring Page** and close the alert. Since the incident was validated as a real threat, mark it as a **True Positive** and include a closing note.  
![Close Alert](https://github.com/user-attachments/assets/a1af505b-de03-49f6-adb6-3720d1548755)

---

Thank you for following through the investigation process. Stay vigilant, and happy incident investigating!  
