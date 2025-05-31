# Controls and Compliance  and Risk Assessment Report

## Scenario

This scenario is based on a fictional company:

Botium Toys is a small U.S. business that develops and sells toys. The business has a single physical location, which serves as their main office, a storefront, and warehouse for their products. However, Botium Toy’s online presence has grown, attracting customers in the U.S. and abroad. As a result, their information technology (IT) department is under increasing pressure to support their online market worldwide. 

The manager of the IT department has decided that an internal IT audit needs to be conducted. She's worried about maintaining compliance and business operations as the company grows without a clear plan. She believes an internal audit can help better secure the company’s infrastructure and help them identify and mitigate potential risks, threats, or vulnerabilities to critical assets. The manager is also interested in ensuring that they comply with regulations related to internally processing and accepting online payments and conducting business in the European Union (E.U.).   

The IT manager starts by implementing the National Institute of Standards and Technology Cybersecurity Framework (NIST CSF), establishing an audit scope and goals, listing assets currently managed by the IT department, and completing a risk assessment. The goal of the audit is to provide an overview of the risks and/or fines that the company might experience due to the current state of their security posture.

Your task is to review the IT manager’s scope, goals, and risk assessment report. Then, perform an internal audit by completing a controls and compliance checklist. 

## Case Study

### Scope and goals of the audit

**Scope:** The scope of this audit is defined as the entire security program at Botium Toys.
This includes their assets like employee equipment and devices, their internal network,
and their systems. You will need to review the assets Botium Toys has and the controls
and compliance practices they have in place.

**Goals:** Assess existing assets and complete the controls and compliance checklist to
determine which controls and compliance best practices that need to be implemented
to improve Botium Toys’ security posture.

### Current assets

Assets managed by the IT Department include:
* On-premises equipment for in-office business needs
* Employee equipment: end-user devices (desktops/laptops, smartphones),
remote workstations, headsets, cables, keyboards, mice, docking stations,
surveillance cameras, etc.
* Storefront products available for retail sale on site and online; stored in the
company’s adjoining warehouse
* Management of systems, software, and services: accounting,
telecommunication, database, security, ecommerce, and inventory management
* Internet access
* Internal network
* Data retention and storage
* Legacy system maintenance: end-of-life systems that require human monitoring

### Risk assessment

**Risk description**

Currently, there is inadequate management of assets. Additionally, Botium Toys does
not have all of the proper controls in place and may not be fully compliant with U.S. and
international regulations and standards.

**Control best practices**

The first of the five functions of the NIST CSF is Identify. Botium Toys will need to
dedicate resources to identify assets so they can appropriately manage them.
Additionally, they will need to classify existing assets and determine the impact of the
loss of existing assets, including systems, on business continuity.

**Risk score**

On a scale of 1 to 10, the risk score is 8, which is fairly high. This is due to a lack of
controls and adherence to compliance best practices.

**Additional comments**

The potential impact from the loss of an asset is rated as medium, because the IT
department does not know which assets would be at risk. The risk to assets or fines 
from governing bodies is high because Botium Toys does not have all of the necessary
controls in place and is not fully adhering to best practices related to compliance
regulations that keep critical data private/secure. 

### Control Assessment Checklist

Does Botium Toys currently have this control in place? 

|**Yes/No**|**Control**|**Details**|
|----------|-----------|-----------|
| No| Least Privilege|Least privilege and separation of duties have not been implemented.   |
| No| Disaster recory plans|There are no disaster recovery plans currently in place.        |
| No| Password policies|Password policy exists, but its requirements are nominal and not in line with current industry standard.|
| No| Separation of duties|Separation of duties have not been implemented.                  |
| Yes| Firewall|The IT department has a firewall that blocks traffic                        |
| No| Intrusion detection system(IDS)|The IT department has not installed an IDS            |
| No| Backups|The company does not have backups of critical data.                           |
| Yes| Antivirus software|Antivirus software is installed and monitored regularly by the IT department.|
| No| Manual monitoring, maintenance, and intervention for legacy systems|There is no regular schedule in place for these tasks and intervention methods are unclear.|
| No| Encryption|Encryption is not currently used to ensure confidentiality of customer's PII and SPII.|
| No| Password management system| There is no centralized password management system that enforces the password policy’s minimum requirements.                                       |
| Yes| Locks (offices, storefront, warehouse)|The store’s physical location, which includes main offices, storefront, and warehouse of products, has sufficient locks.                       |
| Yes| (CCTV)|The store main office, storefront, and warehouse has an up-to-date closed-circuit television (CCTV) surveillance.|
| Yes| Fire detection/prevention|The store main office, storefront, and warehouse has functioning fire detection and prevention systems.|

### Compliance Checklist

Does Botium Toys currently adhere to this compliance best practice?

* Payment Card Industry Data Security Standard (PCI DSS)

| **Yes/No**      | **Best practice**                                                    |
|-----------------|----------------------------------------------------------------------|
| No              | Only authorized users have access to customers’ credit card information.                                             |
| No              | Credit card information is stored, accepted, processed, and transmitted internally, in a secure environment.                                               |
| No              | Implement data encryption procedures to better secure credit card transaction touchpoints and data.                                                  |
| No              | Adopt secure password management policies.                           |

* General Data Protection Regulation (GDPR)

| **Yes/No**      | **Best practice**                                                    |
|-----------------|----------------------------------------------------------------------|
| No              | E.U. customers’ data is kept private/secured.                        |
| Yes             | There is a plan in place to notify E.U. customers within 72 hours if their data is compromised/there is a breach.                                                   |
| No              | Ensure data is properly classified and inventoried.                  |
| Yes             | Enforce privacy policies, procedures, and processes to properly document and maintain data.                         |

* System and Organizations Controls (SOC type 1, SOC type 2)

| **Yes/No**      | **Best practice**                                                    |
|-----------------|----------------------------------------------------------------------|
| No              | User access policies are established.                                |
| No              | Sensitive data (PII/SPII) is confidential/private.                   |
| Yes             | Data integrity ensures the data is consistent, complete, accurate, and has been validated.                 |
| No              | Data is available to individuals authorized to access it.            |

### Recommendations (optional)

To improve the security posture of Botium Toys, several actions are recommended.

  1. Access controls should be implemented based on Least Privilege to ensure employees have access only to the data necessary for their roles.
  2. Enforcing separation of duties to minimize risk of unauthorized access to sensitive data.
  3. Strong encryption for all sensitive data must be utilized when handling PII and SPII.
  4. IDS should be utilized to monitor and detect security breaches.
  5. A disaster recovery plan should be implemented and to be backup regularly to outline clear procedures for security incidents, natural disasters, and other disruptions.
  6. Password policies must be implemented to align with industry standards.
  7. Regular audits need to be completed and additional measures like access controls should be considered for sensitive areas.


