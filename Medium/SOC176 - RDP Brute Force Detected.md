# SOC176 - RDP Brute Force Detected
## Overview

![overview](https://github.com/user-attachments/assets/15cef05b-1824-426d-a651-d46ed2dd48cf)

hey, huys welcome back, today alert investigation is about RDP Brute force detected by security system.
So lets start the investigation by taking ownership of the alert.

Then clikc on create case by clicking on create case button.

![create case](https://github.com/user-attachments/assets/31d455a3-209a-4063-97f6-b3bcd8fc6095)

So start with clicking on start playbook to find the answers for many questions.

![incident details](https://github.com/user-attachments/assets/4e53f1ee-325e-411f-bcc6-18e36bbbe2c7)

Initially we need to find that whether the enrinchment and context is external or internal, as the source ip address is from extrernal, click on external.

![context](https://github.com/user-attachments/assets/c9539205-2ffd-4e69-87fc-1f378d3c4aac)

Then finding the reputaution checking of Source ip address in various sites, from letsdefend treat intell found it as malicious
![treat intell](https://github.com/user-attachments/assets/f1e282e1-c7aa-49b0-99d9-f95b60a491b7)

And from virustotal 14 vendors flagged this ip address as malicious.
![virustotal](https://github.com/user-attachments/assets/b5ded556-79ac-4e02-a44f-37eae0089817)

And finally from abuseipdb site, it gave abuse percentage as 100 and this ip address found more than 4 lakh times in their database.
It has bad reputation.

![abusipdb](https://github.com/user-attachments/assets/aa392d71-ee84-4670-a769-10ae1da6e832)

click on yes as it is suspicious.
Now look at log management for any logs that attacker ip was there in logs regarding of RDP protocol.

![traffic analysis](https://github.com/user-attachments/assets/f9f7fd52-7f7c-4704-9df3-3f769c7cdf65)

Yes there are logs related to bruteforcing the RDP login into the system remotely, tried to login with many times wth different usernames and passwords, finally at some point
the attack was successful with logon.

![determine scope](https://github.com/user-attachments/assets/aa5563f1-bfb0-42da-a5d8-cae87daf3968)

Does the Attacker IP address try to establish an SSH/RDP connection with multiple servers/clients as the target? As the attacker IP address only targets the one system, click on NO.

![log management](https://github.com/user-attachments/assets/1cca3e9c-92b7-49ea-aa33-9b46596904bd)
there are logs related to bruteforcing the RDP login into the system remotely, tried to login with many times wth different usernames and passwords, finally at some point
the attack was successful with evemt id 4624. Click on yes.


![isolated](https://github.com/user-attachments/assets/173ee49a-0034-4af8-a06d-d940257c74f3)

Systems exposed to a cyber-attack should be isolated to reduce the impact of the cyber-attack.  Yes it is necessary to isolate to restrict the exposing the data.

So contain the device to restrict the breach the data.
![containment](https://github.com/user-attachments/assets/8f3ec9f3-9d47-4857-b65d-2a4fd477c7c0)

There is post incident phase which is lessons learned, 
How did the cyber attack happen?
How well did staff and management perform in dealing with the incident?
What would the staff and management do differently the next time a similar incident occurs?
What corrective actions can prevent similar incidents in the future?
What precursors or indicators should be watched for in the future to detect similar incidents?

Enter artifacts, here only two are there src and dst ip addresses.

Analysis note, Analysis confirmed that the brute force attack was successful, there were many attempts to login into system using RDP protocol, and contain system to restrict the data expose.

![finish playbook](https://github.com/user-attachments/assets/c52f6cdf-7d68-4282-ab2f-51e786347436)

So finally the playbook has finished the investigation process and found that it is real alert. click on finish.

![close alert](https://github.com/user-attachments/assets/bf9ac198-28df-4554-96b5-3797b2855ce2)

Click on true positive of the option and write some note, the alert is true.

