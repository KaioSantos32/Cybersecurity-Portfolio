___
**Scenario**: The company stores information on a remote database server, since many of the employees work remotely from locations all around the world. Employees of the company regularly query, or request data from the server to find potential customers. The database has been open to the public since the company's launch three years ago. As a cybersecurity professional, you recognise that keeping the database server open to the public is a serious vulnerability.
You are tasked to completing a vulnerability assessment of the situation to communicate potential risks to decision makers at the company. You must create a written report that explains how the vulnerable server is a risk to business operations and how it can be secures.

# Step 1: Review information about the vulnerable server
## **Purpose for the assessment**
	
As the server database is the core component for the storage of the company, it carries a great importance to the business continuity. It’s important for the data it hold to keep secure and safe for the purpose of stealing secret information and business credibility. If the security is inefficient or fails to attend security standards, customers may not trust the company and current projects or deals may not be able to be fulfilled.

## **Potential Threats**
	


| **Threat source**  | **Threat event**                                           | **Likelihood** | **Severity** | **Risk** |
| ------------------ | ---------------------------------------------------------- | -------------- | ------------ | -------- |
| Competitor         | Obtain sensitive information via exfiltration              | 1              | 3            | 3        |
| Internal leak      | Internal users (employees) stealing or leaking information | 2              | 3            | 6        |
| Malicious software | Conduct man-in-the middle attacks; Delete data;            | 3              | 3            | 9        |
# Step 2: Propose security recommendations
## Approach
	
The approach made for this small evaluation was made upon previous knowledge, since the database is open there is a high chance of external actors to create disturbance on the company's network and storage. The likelihood and severity was scored base on the core business of the company that is interaction with the client, so the information gathered and stored is of high importance for the business continuity.

# Step 3: Remediation Strategy
	
For security reasons, the server need to be closed to the public in general and MFA must be applied to improve the security and manage who connects to the server. After MFA, we must implement the Principle of Least Privilege, to organize the minimum access for the employees and what they can see and edit, preventing major internal leaks. After that, Defense in Depth comes to action to start scanning for threats and vulnerabilities all over the server.