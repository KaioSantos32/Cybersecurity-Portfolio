**Scenario**: 
	You're the first cybersecurity professional hired by a growing business.
	Recently a deposit was made from the business to an unknown bank account. The finance manager says they didn't make a mistake. Fortunately, they were able to stop the payment. The owner has asked you to investigate what happened to prevent any future incidents.

# Step 1: Reviewing incident with log
	
# Incident Log

| **Incident Log**                  |
| --------------------------------- |
| Event Type: Information           |
| Event Source: AdsmEmployeeService |
| Event Category: None              |
| Event ID: 1227                    |
| Date: 10/03/2023                  |
| Time: 8:29:57 AM                  |
| User: Legal\Administrator         |
| Computer: Up2-NoGud               |
| IP: 152.207.255.255               |
| Description:                      |
| Payroll event added. FAUX_BANK    |
# Employees directory

| **Name**          | **Role**         | **Email**              | **IP Address**  | **Status** | **Authorisation** | **Last Access**              | **Start date** | **End date** |
| ----------------- | ---------------- | ---------------------- | --------------- | ---------- | ----------------- | ---------------------------- | -------------- | ------------ |
| Lisa Lawrence     | Office manager   | l.lawrence@erems.net   | 118.119.20.150  | Full-time  | Admin             | 12:27:19 pm (0 minutes ago)  | 01-10-2019     | N/A          |
| Jesse Pena        | Graphic designer | j.pena@erems.net       | 186.125.232.66  | Part-time  | Admin             | 4:55:05 pm (1 day ago)       | 16-11-2020     | N/A          |
| Catherine Martin  | Sales associate  | catherine_M@erems.net  | 247.168.184.57  | Full-time  | Admin             | 12:17:34 am (10 minutes ago) | 01-10-2019     | N/A          |
| Jyoti Patil       | Account manager  | j.patil@erems.net      | 159.250.146.63  | Full-time  | Admin             | 10:03:08 am (2 hours ago)    | 01-10-2019     | N/A          |
| Joanne Phelps     | Sales associate  | j_phelps123@erems.net  | 249.57.94.27    | Seasonal   | Admin             | 1:24:57 pm (2 years ago)     | 16-11-2020     | 31-01-2020   |
| Ariel Olson       | Owner            | a.olson@erems.net      | 19.7.235.151    | Full-time  | Admin             | 12:24:41 pm (4 minutes ago)  | 01-08-2019     | N/A          |
| Robert Taylor Jr. | Legal attorney   | rt.jr@erems.net        | 152.207.255.255 | Contractor | Admin             | 8:29:57 am (5 days ago)      | 04-09-2019     | 27-12-2019   |
| Amanda Pearson    | Manufacturer     | amandap987@erems.net   | 101.225.113.171 | Contractor | Admin             | 6:24:19 pm (3 months ago)    | 05-08-2019     | N/A          |
| George Harris     | Security analyst | georgeharris@erems.net | 70.188.129.105  | Full-time  | Admin             | 05:05:22 pm (1 day ago)      | 24-01-2022     | N/A          |
| Lei Chu           | Marketing        | lei.chu@erems.net      | 53.49.27.117    | Part-time  | Admin             | 3:05:00 pm (2 days ago)      | 16-11-2020     | 31-01-2020   |
# Notes
	
The log contains information about the operation and usage of the system.
We can see that the transference was made in an administrator account from the legal team at 10/03/23, 8:29:57 in the morning on the PC with the name of "Up2-NoGud".
With this information we can check the employees table we can say primarily that the computer of Robert Taylor Jr. was invaded or have a malware, since the IP and role are similar to the log event: 
- Member os Legal team;
- Same IP address;
- Administrator authorisation;

But this account last entry was in 27-12-2019 so the company this is also an issue with the termination or deactivation of old accounts.

# Conclusion

| **Note(s)**                       | **Issue(s)**                                                                                                                                                        | **Recommendation(s)**                                                                                                                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Authorization /authentication** | The incident was caused by an administrator from the legal team with the IP of 152.207.255.255 at 10/03/2023, 8:29:57 AM on the computer with the name "Up2-NoGud". | **Objective:** Based on your notes, list 1-2 authorization issues:<br><br>The user has administration level of authorisation all the time, so the company is not following the least privilege principle or even the separation of duties.<br>Another recommendation is that should be review all the company's accounts and deactivate the ones that are not used in the present, this would prevent leaks and misuse of these old accounts. | **Objective:** Make at least 1 recommendation that could prevent this kind of incident:<br><br>First thing to do is clean the system of old accounts, deactivating them with basis on their last use date.<br>Second, is recommended to start using the least privilege principle, avoiding accounts to have administrator authorisation all the time;<br>Third, should be implemented the separation of duties to avoid an only account having permissions to too much information that is not needed to them. |
