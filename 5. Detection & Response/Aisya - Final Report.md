# Final Report

## Scenario

The organization experienced a security incident on May 23, 2025, at 7:20 p.m., PT, during which an individual was able to gain unauthorized access to customer personal identifiable information (PII) and financial information. Approximately 50,000 customer records were affected. The financial impact of the incident is estimated to be $100,000 in direct costs and potential loss of revenue. The incident is now closed and a thorough investigation has been conducted.

At approximately 3:13 p.m., PT, on May 23, 2025, an employee received an email from an external email address. The email sender claimed that they had successfully stolen customer data. In exchange for not releasing the data to public forums, the sender requested a $25,000 cryptocurrency payment. The employee assumed the email was spam and deleted it.

On May 25, 2025, the same employee received another email from the same sender. This email included a sample of the stolen customer data and an increased payment demand of $50,000. 

On the same day, the employee notified the security team, who began their investigation into the incident. Between May 25 and May 30, 2025, the security team concentrated on determining how the data was stolen and the extent of the theft.

## Executive Summary  

On May 23, 2025, at approximately 7:20 p.m. PT, our organization experienced a data breach where an unauthorized individual gained access to approximately 50,000 customer records, comprising Personal Identifiable Information (PII) and financial data. The incident was initially identified following a second extortion email received by an employee on May 25, 2025, which included a sample of the stolen data and an increased ransom demand. The financial impact is estimated at $100,000 in direct costs and potential revenue loss. A thorough investigation was conducted, and the incident has been successfully contained and remediated.

## Timeline  

  * **May 23, 2025, 3:13 p.m.:** Employee receives the first extortion email from an external address, claiming data theft and demanding a $25,000 cryptocurrency payment for non-disclosure. Employee deletes the email, deeming it spam.
  * **May 23, 2025, 7:20 p.m.:** Estimated time of unauthorized access to customer PII and financial information. (Identified retrospectively during investigation).
  * **May 25, 2025:** Same employee receives a second extortion email from the same sender, including a sample of stolen customer data and an increased demand of $50,000.
  * **May 25, 2025:** Employee notifies the security team.
  * **May 25 - May 30, 2025:** Security team conducts intensive investigation to determine the method and extent of data exfiltration.
  * **May 30, 2025 - May 31, 2025:** Containment and remediation activities, detailed analysis, and report generation.
  * **May 31, 2025:** Incident closed.

## Investigation  

The investigation findings indicate that the threat actor gained unauthorized access to our systems, leading to the exfiltration of approximately 50,000 customer records. The method of initial compromise is still under detailed forensic analysis but appears to have leveraged a vulnerability or misconfiguration that facilitated unauthorized access. The two extortion emails served as the initial notification of the breach, rather than the initial attack vector. While the employee initially dismissed the first email, the inclusion of data samples in the second email validated the threat. The exact mechanism of data exfiltration and the specific vulnerability exploited indicated that the attacker accessed the information of thousands of purchase confirmation pages.

## Response and remediation  

The organization collaborated with the public relations department to disclose the data breach to its customers. After the security team reviewed the associated web server logs, the cause of the attack was very clear. There was a single log source showing an exceptionally high volume of sequentially listed customer orders.
The incident was successfully contained, and all known unauthorized access has been mitigated.

## Recommendations

To prevent future recurrences, we are taking the following actions:
  * Vulnerability Management: Perform routine vulnerability scans and penetration testing of all internet-facing systems to identify and patch potential access points. Prioritize patching based on severity and exposure.
  * Implement the following access control mechanisms:
      * Implement allowlisting to allow access to a specified set of URLs and automatically block all requests outside of this URL range.
      * Ensure that only authenticated users are authorized access to content.
  * Incident Response Playbook Review: Conduct a post-incident review of the data breach response playbook to identify areas for optimization and ensure its continued effectiveness against evolving threats.
  * Security Awareness Training: Reinforce and enhance employee security awareness training.
