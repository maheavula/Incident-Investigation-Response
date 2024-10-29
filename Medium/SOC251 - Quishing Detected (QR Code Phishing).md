# SOC251 - Quishing Detected (QR Code Phishing)

## Overview

![overview](https://github.com/user-attachments/assets/c8140446-4424-4118-b5cf-f72adf1ff2f9)

Hey guys welcome back to another alert investigation walk through process, this alert is about Quishing detected which is QR code phishing.
So lets start by taking ownership of alert by clicking on take ownership.

![create case](https://github.com/user-attachments/assets/303ef3d2-6d0d-42bd-b1a4-bb93b81b19f2)

and then from investigation page click on create page to create the case.

![incident details](https://github.com/user-attachments/assets/6ad43186-aa97-480a-94c5-afc18b729587)

To start investigation with the playbook click start playbook and start doing it.

![verify](https://github.com/user-attachments/assets/1942b9fa-a274-4d40-8f7a-8c99642ee497)

Alarms escalated from Tier1 to Tier2 should be caused by a truly harmful event, but escalated alarms by Tier1 analysts are not always True Positive due to technical inadequacy, faulty/incomplete analysis, and authorization problems. Before initiating Incident Response processes, please verify that the alarm from the Tier1 analyst was caused by malicious activity.

So it is required to verify this alarm triggered by true malicious activity or not so click on next to verify the process next.

At this stage it is important of Reconnaissance is an important phase of an attack where the attacker gathers information about the target system and network. This playbook aims to identify potential reconnaissance activity. Click next.

![log channel](https://github.com/user-attachments/assets/b915a2d2-f470-4cdb-a622-09cc010287c5)

After verifying in logs, found a smtp exchange of mail from this IP 158.69.201.47.

![raw log](https://github.com/user-attachments/assets/9702ab20-118f-4590-860b-39317d8b8e3c)

Sender Mail: security@microsecmfa.com
Destination Mail: Claire@letsdefend.io
Subject: New Year's Mandatory Security Update: Implementing Multi-Factor Authentication (MFA)
those are the header details of mail.

Look for any unusual or suspicious domain name requests. Check for any unusual or suspicious HTTP requests. Look for any unusual or suspicious DNS requests. Against phishing for information, check email security. You can check Endpoint Security and Email Security for related searches.
Yes, after looking at email secuirty, found a mail with regards of Claire user, in that mail is about microsoft company  multi factor authentication, but the Domain of the sender is not from legit Domain of microsoft, so it is suspicious here.
Sender Mail: security@microsecmfa.com
![qr code](https://github.com/user-attachments/assets/385f3966-bc8f-4a9d-8692-550b1d52b68c)

As a result of the analysis made through Endpoint Security analysis which Reconnaissance technique does the attack match?, it is Phishing for information, click on it
![reconnaissance](https://github.com/user-attachments/assets/a1e0a72e-0434-4bf1-a088-4327edc8440d)

The attacker performing the Recon activity can be detected from the logs on IP Log Management. Is the attacker IP internal or external?, The attacker IP is from external because it is public IP address.

![attacker ip analysis](https://github.com/user-attachments/assets/72d205e7-6b8a-459f-b63b-556c6ba900c3)

Now we should check the IP reputation in online sources, 

![threat intel](https://github.com/user-attachments/assets/04859967-88cb-457e-849e-854cadbeaeee)

from letsdefend threat intel it is under is a phishing category.

![virustotal](https://github.com/user-attachments/assets/6dfca777-a093-47fb-a924-66c02e3ab48b)

and from virus total 12 vendors flagged it as malicious IP address and From abuseipdb the confidence is low but 340 times IP address found in its database.


![determine scope](https://github.com/user-attachments/assets/a1fe9f56-e382-4795-a1cf-2c95c0160be9)

You should fnd which systems are affected. Search on the Endpoint Security, Log Management, and Email Security for IOCs you found during your investigation.
Is there more than one affected device?, No, there is not other device is affected by this attack.

![Contained](https://github.com/user-attachments/assets/1b3af799-ef36-495b-b360-1cf2aabe874b)

So it is necessary of isolating this device to restrict from not spreading this attack. Click on Yes.

Lessons learned by these questions, 
Lesson Learned
How did the cyber attack happen?
How well did staff and management perform in dealing with the incident?
What would the staff and management do differently the next time a similar incident occurs?
What corrective actions can prevent similar incidents in the future?
What precursors or indicators should be watched for in the future to detect similar incidents?

![add artifacts](https://github.com/user-attachments/assets/844a6835-913a-4b46-bab6-974014bc6824)

Add artifacts in the provided space, write IOCs in it.

Write analysis note, According to the investigation, it has confirmed that it is QR phishing attack, the mail domain is not from microsoft, it device is contained from not spreading attack, the reputation of ip is not good from threat intel.
![playbook confirm](https://github.com/user-attachments/assets/993df0a5-b4fb-428c-91dd-6b2be6360dac)

So to save our investigation details and finding will save by click on playbook confirm, so click on confirm button.
![close alert](https://github.com/user-attachments/assets/0c308d1e-d549-4d90-b1ab-32b4315a0e72)

Finally the alert is true positive by detecting alert as qr phishing attack.

