# Security Risk Assessment Report: Analysis of Network Hardening

## Scenario

You are a security analyst working for a social media organization. The organization recently experienced a major data breach, which compromised the safety of their customers’ personal information, such as names and addresses. Your organization wants to implement strong network hardening practices that can be performed consistently to prevent attacks and breaches in the future. 

After inspecting the organization’s network, you discover four major vulnerabilities. The four vulnerabilities are as follows:

  1. The organization’s employees' share passwords.
  2. The admin password for the database is set to the default.
  3. The firewalls do not have rules in place to filter traffic coming in and out of the network.
  4. Multifactor authentication (MFA) is not used. 

If no action is taken to address these vulnerabilities, the organization is at risk of experiencing another data breach or other attacks in the future. 

You will write a security risk assessment to analyze the incident and explain what methods can be used to further secure the network.

## Report

**Part 1: Select up to three hardening tools and methods to implement**

🔧 System Hardening Measures

To address identified vulnerabilities, the following hardening tools and methods are recommended:

  1. Implement Multi-Factor Authentication (MFA)
     Require users to verify identity using multiple authentication methods (e.g., passwords, biometrics, PINs, or security tokens) to reduce the risk of unauthorized access.

  2. Enforce Strong Password Policies
     Define rules for password complexity, minimum length, and allowed characters. Limit failed login attempts and disable accounts after repeated failures to prevent brute-force attacks.

  3. Regular Firewall Maintenance
     Review and update firewall rules and configurations regularly to ensure only authorized traffic is allowed and to mitigate evolving threats.


**Part 2: Explain your recommendations**

🔐 Security Recommendations

1. Enforce Multi-Factor Authentication (MFA)

   MFA adds a second layer of authentication beyond passwords, reducing the risk of brute-force attacks and unauthorized access. It also discourages password sharing, as additional authentication (e.g., OTP or biometric) is required.

2. Implement a Strong Password Policy

   Require complex passwords, regular password changes, and prohibit reuse of old passwords. Lock accounts after a defined number of failed login attempts to prevent brute-force attacks and unauthorized access.



