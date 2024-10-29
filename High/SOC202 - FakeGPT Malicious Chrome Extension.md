# SOC202 - FakeGPT Malicious Chrome Extension

## overview

![overview](https://github.com/user-attachments/assets/3397bca7-cf11-4d50-9a90-98276290ecad)

hey guys welcome back to another walk through high severity alert, it is FakeGPT malicious chrome extension.

So lets start with taking ownership of the alert, and from investigation page click on create case to create the case to investigation. Startt

![create case](https://github.com/user-attachments/assets/a26e43bc-fc39-432a-a77b-7578cf884c08)

So now we have created a case and now to start investigation click on start playbook button from case management page.

![threat indicator](https://github.com/user-attachments/assets/3554426a-0e01-46cb-abb7-36234ab0c829)

Now we need to defien the threat indicator as is it outgoing traffic or incoming or anyother else, so in given options, we dont have certain option so click on other.

![threat indicator](https://github.com/user-attachments/assets/bca1c84f-91fd-498c-a5c1-5bda647bec02)

checking for whether the device is quarantined or not, from endpoint security the device is not quarantined so click on not quarantined.

So as it is not quarantined, we should analyze the extension file in online sanboxes so find it whether as malicious or not, 

![virustotal](https://github.com/user-attachments/assets/9f95d27a-da4f-44ca-9421-33ab7da1b71d)

From virustotal there were no single vendor flagged as malicious, it doest have suspicious behaviour.

![hybrid analysis](https://github.com/user-attachments/assets/c5a7bee7-735f-4235-8003-44f83721d332)

From hybrid analysis also it declared it as cleaned it is not malicious and also from any run, it gave no threat detected. So it is clean and not suspicious.

But from log management history, with this host IP there are http requests, those requests are from two different destination IP addresses, 
18.140.6.45 and 52.76.101.124.

![raw 1](https://github.com/user-attachments/assets/6f36678c-a0e9-4df9-9b16-6b62976da678)
![raw log](https://github.com/user-attachments/assets/d8a89dde-489b-4244-860b-ad6ea5100624)

The destination name are looking suspicious because the legit chatgpt domain different to this requested domain. So it is malicious.

![accessed](https://github.com/user-attachments/assets/f206c8b9-d23c-4617-bf4c-ee8e0d8d7852)

Yes, the device accessed the C2 address by searching from browser, there are related logs and browser history of accessing it. so click on accessed.

![containment](https://github.com/user-attachments/assets/5903bb6e-5c22-4d22-83c3-1c1de3df7370)
![host contain](https://github.com/user-attachments/assets/7e1ae74c-dce9-4317-824e-3397a6113b85)

To restrict the attack vector, it is necessary of containing the host device so go to security device and contain it.

![add artifacts](https://github.com/user-attachments/assets/26c69ec5-2048-4ccd-9f1c-78f468f0e8c0)

Enter artifacts into blanks. Those are IOCs of alert.

Write analysis note, According to the investigation, it has confirmed that it is a malicious extension, alert triggered was true positive, the host was contained to restrict spreading of attack.
![confirm](https://github.com/user-attachments/assets/4fafdc8f-8d08-493f-a572-e8b0634f4ae5)

At last to close the investigation, and to confirm the playbook to saving all investigation traces and data.

![close alert](https://github.com/user-attachments/assets/6ba8f942-fa70-4f6a-836d-f41fec47e4dd)

Finally it is a true positive alert triggered by security device, the extension was a fake and malicious file.

