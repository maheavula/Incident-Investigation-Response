#  SOC173 - Follina 0-Day Detected

## Overview

![overview](https://github.com/user-attachments/assets/38b48952-98e0-42d9-97ba-e2f39f0c2bd8)

Hey guys welcome back to this vigilant incident and investigation of a Zero data detection,

lets start with taking owenership of this alert.
From investigation channel, create a case by clicking on create case.
![create case](https://github.com/user-attachments/assets/e39a0b03-e7b2-4cec-81f7-eb3d0d43bbc2)

Then it will redirect to case management page to start investigation with playbook, so click on start playbook.
![incident details](https://github.com/user-attachments/assets/f542c099-caca-406f-811a-17cead176ac4)

Right now, we have to define threat indicator by selecting the traffic flow options, as the alert triggered by opening a doc file and then another .exe file executed so it is none of given option click on Other.

![threat indicator](https://github.com/user-attachments/assets/ab868c14-63db-47f7-9393-30c0dc355791)

Now we should check for the whether malware is quarantined or not by looking into logs and endpoint security. After looking at endpoint device, the device did not quarantine.

![quarantined or not](https://github.com/user-attachments/assets/2e6f1775-91ce-42d6-9a57-705d1ee200e1)


By analysis malware hash in various tools, they have confirmed it as a malicious and it is under trojan and downloader category.
![Analyze malware](https://github.com/user-attachments/assets/964bf0af-8455-4b1e-ae97-83d997ba954e)

In virustotal, 48 vendors flagged it as malicious file.
![virustotal](https://github.com/user-attachments/assets/0ae14781-a8c6-4f32-8298-77b3e53e592e)

In hybrid analysis, the threat score is 100/100 and AV detection is 79%, so it aslo confirmed as malcious file.
![hybrid analysis](https://github.com/user-attachments/assets/36efc26c-97a4-4889-9af6-cf980e5dad9d)

Ans in anyrun sanbox, it gave with cvv number and score as 100. 
![anyrun](https://github.com/user-attachments/assets/d41d158f-f6ce-4f57-9799-f3dd44b7387b)

So that the file is malicous and click on malicous
![requested c2](https://github.com/user-attachments/assets/a1118083-cc58-44eb-a75f-176254c59db8)
There are few logs requested to C2 with same domains which are suspicious, so user requested C2 and accessed by C2.
![accessed c2](https://github.com/user-attachments/assets/95dc52d7-5da9-40b5-aade-f4e271749e6e)


It is necessary to contain the device to restrict the spreading of malware to other devices in network.
![contained](https://github.com/user-attachments/assets/5a0f304d-90bf-43f4-ba83-38fdfdecb89d)

Add artifacts that found in investigaion process.
![add artifacts](https://github.com/user-attachments/assets/b84ddd3b-0b8e-4370-bf3c-df80297f95d9)

Write analysis note, According to the investigation, it has confirmed that it is malicious file, categorized as trojan and downloader, it has requested to C2, so contained it, 48 vendors flagged it as malware.

So finally by clicking on confirm button, the investigation process and findings will saved, click on confirm.
![finish playbook](https://github.com/user-attachments/assets/4ad86ffc-d684-49c8-ab1b-13bf2ac708cd)

![close alert](https://github.com/user-attachments/assets/78da7fe4-d405-4782-a6aa-8c7a1f9244ff)

So to close this alert, report it as positive alert, beacause of it is a malware file. 
