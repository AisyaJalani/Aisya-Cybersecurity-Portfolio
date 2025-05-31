# NIST Cybersecurity Framework : Incident Report Analysis

## Scenario

You are a cybersecurity analyst working for a multimedia company that offers web design services, graphic design, and social media marketing solutions to small businesses. Your organization recently experienced a DDoS attack, which compromised the internal network for two hours until it was resolved.

During the attack, your organization’s network services suddenly stopped responding due to an incoming flood of ICMP packets. Normal internal network traffic could not access any network resources. The incident management team responded by blocking incoming ICMP packets, stopping all non-critical network services offline, and restoring critical network services. 

The company’s cybersecurity team then investigated the security event. They found that a malicious actor had sent a flood of ICMP pings into the company’s network through an unconfigured firewall. This vulnerability allowed the malicious attacker to overwhelm the company’s network through a distributed denial of service (DDoS) attack. 

To address this security event, the network security team implemented: 

  * A new firewall rule to limit the rate of incoming ICMP packets
  * Source IP address verification on the firewall to check for spoofed IP addresses on incoming ICMP packets
  * Network monitoring software to detect abnormal traffic patterns
  * An IDS/IPS system to filter out some ICMP traffic based on suspicious characteristics

As a cybersecurity analyst, you are tasked with using this security event to create a plan to improve your company’s network security, following the National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF). You will use the CSF to help you navigate through the different steps of analyzing this cybersecurity event and integrate your analysis into a general security strategy. We have broken the analysis into different parts in the template below. You can explore them here:

  * **Identify** security risks through regular audits of internal networks, systems, devices, and access privileges to identify potential gaps in security.
  * **Protect** internal assets through the implementation of policies, procedures, training and tools that help mitigate cybersecurity threats.
  * **Detect** potential security incidents and improve monitoring capabilities to increase the speed and efficiency of detections.
  * **Respond** to contain, neutralize, and analyze security incidents; implement improvements to the security process.
  * **Recover** affected systems to normal operation and restore systems data and/or assets that have been affected by an incident.

## Incident Report Analysis

**Summary**

The company experienced a DDoS attack using a high volume of ICMP packets, which caused all network services to become unresponsive. The cybersecurity team mitigated the attack by blocking ICMP traffic and pausing non-critical services to restore core functionality.|

**🔍 Identify** 
  * Threat Actor: Unknown (External)
  * Attack Vector: ICMP echo request (ping flood)
  * Scope: Entire internal network
  * Assets Impacted: Core network services, user access systems, internal applications|

**🛡 Protect**
  * Implemented firewall rate-limiting for ICMP traffic
  * Deployed Intrusion Detection/Prevention System (IDS/IPS) to filter suspicious ICMP patterns

**👁 Detect** 
  * Enabled source IP verification on firewall to block spoofed ICMP packets
  * Deployed network monitoring tools to detect abnormal traffic patterns and DDoS indicators

**🛠 Respond**  
  * Blocked incoming ICMP traffic at the perimeter firewall
  * Isolated affected systems to prevent further disruption
  * Temporarily disabled non-critical network services
  * Analyzed logs to identify indicators of compromise and attack origin
  * Escalated the incident to management and prepared reports for possible legal reporting

**🔄 Recover** 
  * Restored critical network services first
  * Confirmed attack subsided before reactivating non-critical systems
  * Validated stability through monitoring before full system restoration
  * Reviewed firewall and IDS/IPS logs post-recovery for assurance





