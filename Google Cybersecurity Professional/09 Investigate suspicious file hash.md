___
**Scenario**: 
	You are a level one SOC analyst at a financial services company. You've received an alert about a suspicious file being downloaded on a computer. After investigating the alert, you discovered that the employee received an email containing an attachment, protected by a password given on the email. 
	The file was a spreadsheet and when it was opened, a malicious payload was executed along on their computer.
	Now that you have the file, you created a SHA256 hash of that file for further analysis.

# 1. Review of the incident
	
hash of the file: 54e6ea47eb04634d3e87fd7787e2136ccfbcc80ade34f246a12cf93bab527f6b

## Timeline of events

| **Time** | **Action**                                                                                     |
| -------- | ---------------------------------------------------------------------------------------------- |
| 1:11 p.m | An employee reveives an email containing a file attachment.                                    |
| 1:13 p.m | The employee successfully downloads and opens the file.                                        |
| 1:15 p.m | Multiple unauthorized executable files are created on the computer.                            |
| 1:20 p.m | The intrusion detection system detects the executable files and sends out an alert to the SOC. |

# 2. VirutTotal analysis
	
We'll use the hash for the analysis, the feedback is the following (one part):
![[9_1_virus_total_analysis.png]]

Based on this feedback, it's safe to consider that the file is a malware since most vendors has declared it as such.