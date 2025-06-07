# Capture first packet with Tcpdump

## Scenario  

You’re a network analyst who needs to use `tcpdump` to capture and analyze live network traffic from a Linux virtual machine.
The lab starts with your user account, called `analyst`, already logged in to a Linux terminal.
Your Linux user's home directory contains a sample packet capture file that you will use at the end of the lab to answer a few questions about the network traffic that it contains.

  You must filter the data in order to:
  * Identify network interfaces
  * Use the `tcpdump` command to capture network data for inspection
  * Interpret the information that `tcpdump` outputs regarding a packet, and
  * Save and load packet data for later analysis.


**1. Identify network interfaces**

  * The `ifconfig` used to identify the interfaces that are available. The Ethernet network interface is identified by the entry with the `eth` prefix.
  * The `tcpdump -D` used to identify the interface options available for packet capture. This also allows us to identify which network interfaces are available.

<img width="717" alt="netmask 255 255 0 0" src="https://github.com/user-attachments/assets/23f42885-6857-4ed2-9a2d-41ff205cbe15" /><br/>

<img width="716" alt="AD_4nXeRjOe79einGzS1QqdLMMz8AphrPq3ntgRUFcjq-IjtATNE93lDnLS8kRDQCcZMOpwEthxLsWW85sKtBhqW3VU3Xq4sCl9tuyv0fG7PxQl6cmDQmVFhmlVW" src="https://github.com/user-attachments/assets/e3d372d4-2231-4682-93d8-f7cc360bf35e" /><br/>


**2. Capture network data for inspection**

* The `sudo tcpdump -i eth0 -v -c5` is to filter live network packet data from the eth0 interface with `tcpdump`. The command `-i eth0` is to capture data specifically from the eth0 interface. `-v` command will display detailed packet data and `-c5` command captures 5 packets of data.

<img width="717" alt="AD_4nXd-2vianMg6t3Jamsj-dA6GzGaV-soMepPU-0Sk30sTX2lWbTVZT_8tNzQy3Aic-5pjaJdhzfyFmF3TajDd_zy7WdgEWTCaHVmSQN-TrK6rGqJu5_9Gz3KO" src="https://github.com/user-attachments/assets/737bd39d-8733-4688-be2d-d7f1f2d26368" /><br/>

* The `tcpdump: listening on eth0, link-type EN10MB (Ethernet), capture size 262144 bytes` which show the `eth0` as the interface, and it provided information on the link type and the capture size in bytes.
* The `03:16:01:911848 IP`, is the packet's timestamp, followed by the protocol type, IP.
* The verbose option, `-v`, has provided more details about the IP packet fields, such as TOS, TTL, offset, flags, internal protocol type (in this case, TCP (6)), and the length of the outer IP packet in bytes: `(tos 0x0`, `ttl 64`, `id 28774`, `offset 0`, `flags [DF]`, `proto TCP (6)`, `length 119)`
* The data `b21c06c3d611.5000 > nginx-us-east1-c.c.qwiklabs-terminal-vms-prod-00.internal.44728:` shows the systems that are communicating with each other
  * `tcpdump` will convert IP addresses into names, as in the screenshot. The name of the Linux virtual machine, also included in the command prompt, appears here as the source for one packet and the destination for the second packet. In the live data, the name will be a different set of letters and numbers.
  * The direction of the arrow `(>)` indicates the direction of the traffic flow in this packet. Each system name includes a suffix with the port number (.5000 in the screenshot), which is used by the source and the destination systems for this packet.
* The header data for the inner TCP packet `Flags [P.]`, `cksum 0x5892 (incorrect > 0x6db7)`, `seq 3264834579:3264834646`, `ack 3226143523`, `win 492`, `options [nop,nop,TS val 1059717295 ecr 4258455653]`, `length 67`: 
  * The `flags` field identifies TCP flags. In this case, the `P` represents the push flag and the period indicates it's an ACK flag. This means the packet is pushing out data.
  * The next field is the TCP `checksum` value, which is used for detecting errors in the data.
  * This section also includes the sequence and acknowledgment numbers, the window size, and the length of the inner TCP packet in bytes.
 
**3. Capture network traffic**

* The `sudo tcpdump -i eth0 -nn -c9 port 80 -w capture.pcap &` is used to capture packet data into a file called `capture.pcap`

<img width="717" alt="AD_4nXchbMpCYQhckiZz8snAeqZZRO1fTUmD3dPM0FwKYbDcpGwHMMvCpwoK6q-LdDvAg32xdwDVi3EIMmhNYODRlosGVyVd6OjD1cI7odTFJM3fjo1LixFZNmDX" src="https://github.com/user-attachments/assets/41ac91e5-4aa6-4425-90af-80130e97e473" /><br/>

* `-i eth0`: Capture data from the eth0 interface.
* `-nn`: Do not attempt to resolve IP addresses or ports to names.This is best practice from a security perspective, as the lookup data may not be valid. It also prevents malicious actors from being alerted to an investigation.
* `-c9`: Capture 9 packets of data and then exit.
* `port 80`: Filter only port 80 traffic. This is the default HTTP port.
* `-w capture.pcap`: Save the captured data to the named file.
* `&`: This is an instruction to the Bash shell to run the command in the background.
<br/>

<img width="718" alt="AD_4nXcycD_M7JSWpgYbHF5r02qUsv-HysHBgYrZ_0J0je_RnMMdLqub3f7SOFFm3SegEXdO9nxpVKnK-2-9ZXaoCnJVsaHurwFBXjuVcN4RLax1LzgBKgUQlSiW" src="https://github.com/user-attachments/assets/34e30bf3-cea7-40a0-96c0-a76b511e333f" /><br/>

* Use `curl` to generate some HTTP (port 80) traffic. it generates some HTTP (TCP port 80) traffic that can be captured.
* The `ls -l` is to verify that packet data has been captured.

<img width="718" alt="AD_4nXczSTF7TtH0T_PQiE-nVA3BewNWHE0Y8qHAZ4cO9JTY1q8U5gEAgo0tqfq9KyGpsrNFEYHOm4VnqS_f0X8zc-qAOdkygJpgcIWJMp9n1kFDH-2SMPLtopf-" src="https://github.com/user-attachments/assets/10de578a-77bd-494b-8a1a-975f18cc994e" /><br/>

**4. Filter the captured packet data**

* Use the `sudo tcpdump -nn -r capture.pcap -v` command to filter the packet header data from the `capture.pcap` capture file. The `-nn` is to disable port and protocol name lookup. `-r` is to read capture data from the named file. `-v` is to display detailed packet data.

<img width="718" alt="AD_4nXdPe1goGOH8wE_dgWZ4fI4JPrBWeiOYGWBuYVHFTdR3kIxwp9_iQ4JwcdGxil_tNyaJ4Fo9LyIzCT6v4Sq2-V-xyXSOnDcMpgC7hoRKfljEc_MwrCImQqXh" src="https://github.com/user-attachments/assets/0e99fa3f-2328-43e8-be9d-82d9de53f45f" /><br/>

* The `sudo tcpdump -nn -r capture.pcap -X` command to filter the extended packet data from the `capture.pcap` capture file. The `-nn` is to disable port and protocol name lookup. `-r` is to read capture data from the named file. `-X` is to display the hexadecimal and ASCII output format packet data. Security analysts can analyze hexadecimal and ASCII output to detect patterns or anomalies during malware analysis or forensic analysis.

![AD_4nXfVS0_dR62FTez6QPyCGpqgcZlwz_yCJfvMLT2R47XdrsWq7S3RBXSE8ZeaU4Ff2ZyHQEXZLmjBHDq-Q-V_D0q4VSe7-AkJo6dQ8ktBMvH46-lcLUYM_NU7](https://github.com/user-attachments/assets/33c970f2-2201-425d-aaf7-6e96aa3feb40)<br/>

![AD_4nXffsb03iKOp7RGdABuYPSarDFUVG06UJsd7o_1Vt8xW5izsO1jMCJQfq_uyltORlxghb8aD_z0xdAai-SefzWDzSYJJXjuOjdiQeOKq0B8__WTWY9Rd3yh3](https://github.com/user-attachments/assets/b20019a8-e9a8-49df-9868-0d39fb840271)

















    
