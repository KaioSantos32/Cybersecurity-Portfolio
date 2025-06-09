___
**Scenario**
	You received a phishing alert about a suspicious file being downloaded on an employee's computer. After investigating the email attachment file's hash, it was declared malicious. Now that you have the information, you must follow the organization's process to complete the investigation and resolve this alert.
	Your organization's security policies and procedures describe how to respond to specific alerts, including what to do when you receive a phishing alert.

# Alert ticket
| **Ticket ID** | **Alert Message**                                         | **Severity** | **Details**                                                                                                                   | **Ticket status** |
| ------------- | --------------------------------------------------------- | ------------ | ----------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| A-703         | SERVER-MAIL Phishing attempt possible download of malware | ==High==     | The user may have opened a malicious email and opened attachments or clicked links.                                           | ==Escalated==     |
|               |                                                           |              | The email contains a lot of grammatical errors, strong indicator of phishing.                                                 |                   |
|               |                                                           |              | Another important point to take in consider is that the "cover letter" is an ".exe" file, executable, not a pdf as it should. |                   |

| Ticker comments |
| --------------- |
| (no coments)    |
### **Additional information**

**Known malicious file hash**: 54e6ea47eb04634d3e87fd7787e2136ccfbcc80ade34f246a12cf93bab527f6b
  
### **Email**:  
From: Def Communications <76tguyhh6tgftrt7tg.su> <114.114.114.114>

Sent: Wednesday, July 20, 2022 09:30:14 AM

To: <hr@inergy.com> <176.157.125.93>  
Subject: Re: Infrastructure ==Egnieer== role
___

Dear HR at ==Ingergy==,  
  
I am writing for to express my interest in the engineer role posted from the website.  
  
There is attached my resume and cover letter. For privacy, the file is password protected. Use the password paradise10789 to open.  
  
Thank you,
  
Clyde West
___
**Attachment**: filename="bfsvc.==exe=="

# 1. Phishing analysis

|                 | Security Incident #01                                                                                                                                                                                                                                                                                                                                                          |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Description** | The error occurred by the lack of email filtering and training for the people using the emails.<br>The email contains an ".exe" saying it's a "cover letter" and it's protected by a password to be accessed.                                                                                                                                                                  |
| **Tools used**  | VirusTotal for verificationof the attachment;                                                                                                                                                                                                                                                                                                                                  |
| **Who**         | Someone with the email "Def Communications <76tguyhh6tgftrt7tg.su>" and IPv4 <114.114.114.114><br>                                                                                                                                                                                                                                                                             |
| **What**        | phishing threat                                                                                                                                                                                                                                                                                                                                                                |
| **Where**       | over the email "hr@inergy\.com <IPv4 176.157.125.93>"                                                                                                                                                                                                                                                                                                                          |
| **When**        | July 20, 2022 09:30:14 AM                                                                                                                                                                                                                                                                                                                                                      |
| **Why**         | Possible malware installed on the computer, needs escalation for a more in depth verification of the complete computer system and extend the verification over to the network, searching for non authorized accesses                                                                                                                                                           |
| **Side notes**  | The sender's IP should be blocked or at least put into quarantine.<br>After the hash analysis with VirusTotal, the executable was considered malicious and should be treated carefully and the receiver's machine should be isolated.<br>The executable should be analysed in a controlled system in order to understand it's doings over the system and possibly network.<br> |
