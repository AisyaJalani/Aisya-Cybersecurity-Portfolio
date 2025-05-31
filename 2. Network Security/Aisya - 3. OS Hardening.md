# Security Incident Report: OS Hardening

## Scenario

You are a cybersecurity analyst for yummyrecipesforme.com, a website that sells recipes and cookbooks. A former employee has decided to lure users to a fake website with malware. 

The former employee/ hacker executed a brute force attack to gain access to the web host. They repeatedly entered several known default passwords for the administrative account until they correctly guessed the right one. After they obtained the login credentials, they were able to access the admin panel and change the website’s source code. They embedded a javascript function in the source code that prompted visitors to download and run a file upon visiting the website. After embedding the malware, the hacker changed the password to the administrative account. When customers download the file, they are redirected to a fake version of the website that contains the malware. 

Several hours after the attack, multiple customers emailed yummyrecipesforme’s helpdesk. They complained that the company’s website had prompted them to download a file to access free recipes. The customers claimed that, after running the file, the address of the website changed and their personal computers began running more slowly. 

In response to this incident, the website owner tries to log in to the admin panel but is unable to, so they reach out to the website hosting provider. You and other cybersecurity analysts are tasked with investigating this security event.

To address the incident, you create a sandbox environment to observe the suspicious website behavior. You run the network protocol analyzer tcpdump, then type in the URL for the website, yummyrecipesforme.com. As soon as the website loads, you are prompted to download an executable file to update your browser. You accept the download and allow the file to run. You then observe that your browser redirects you to a different URL, greatrecipesforme.com, which contains the malware.  

The logs show the following process:

  1. The browser initiates a DNS request: It requests the IP address of the yummyrecipesforme.com URL from the DNS server.
  2. The DNS replies with the correct IP address.
  3. The browser initiates an HTTP request: It requests the yummyrecipesforme.com webpage using the IP address sent by the DNS server.
  4. The browser initiates the download of the malware.
  5. The browser initiates a DNS request for greatrecipesforme.com.
  6. The DNS server responds with the IP address for greatrecipesforme.com.
  7. The browser initiates an HTTP request to the IP address for greatrecipesforme.com.

A senior analyst confirms that the website was compromised. The analyst checks the source code for the website. They notice that javascript code had been added to prompt website visitors to download an executable file. Analysis of the downloaded file found a script that redirects the visitors’ browsers from yummyrecipesforme.com to greatrecipesforme.com. 

The cybersecurity team reports that the web server was impacted by a brute force attack. The disgruntled hacker was able to guess the password easily because the admin password was still set to the default password. Additionally, there were no controls in place to prevent a brute force attack. 

Your job is to document the incident in detail, including identifying the network protocols used to establish the connection between the user and the website.  You should also recommend a security action to take to prevent brute force attacks in the future.

## Section 1: Identify the network protocol involved in the incident

The protocol involved in this incident is HTTP (Hypertext Transfer Protocol). Since the issue was related to accessing the web server for yummyrecipesforme.com, and web page requests typically use HTTP, it's clear that this protocol was in use. When we ran tcpdump while accessing the site, the log confirmed HTTP traffic. The malicious file was delivered to users' computers via HTTP at the application layer.

## Section 2: Document the incident

Users reported being prompted to download a file from yummyrecipesforme.com that offered new recipes. After running the file, their computers slowed down. The site owner was also locked out of their admin account.

A cybersecurity analyst investigated in a sandbox environment using tcpdump. Visiting the site triggered a file download and redirected the browser to a fake site: greatrecipesforme.com.

Network logs showed initial HTTP traffic to yummyrecipesforme.com, followed by a redirect to greatrecipesforme.com after the file was executed. The downloaded file was confirmed to be malicious.

Analysis revealed that the website was modified to prompt users to install malware disguised as a browser update. It's likely the attacker gained admin access through a brute-force attack, then altered the site content. Running the file led to system compromise.

## Section 3: Recommend one or more remediations for brute force attacks

🔒 Brute-Force Attack Mitigation Measures

To reduce the risk of brute-force attacks, the following security controls will be implemented:

  1. Password Reuse Restriction

     Users will be prohibited from reusing previous or default passwords during password resets. This mitigates the risk of attackers leveraging known or reused credentials to gain unauthorized access.

  2. Password Expiration Policy

     Passwords will be required to be updated at regular intervals. Frequent changes limit the window of opportunity for attackers to exploit compromised credentials.

  3. Two-Factor Authentication (2FA)

     2FA will be enforced for all user logins. In addition to a password, users must verify their identity using a one-time passcode (OTP) sent via email or SMS. This adds an additional layer of authentication, significantly reducing the effectiveness of brute-force attacks.

These measures are designed to strengthen account security and minimize unauthorized access through credential-based attacks.


