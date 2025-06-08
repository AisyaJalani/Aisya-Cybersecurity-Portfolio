# Analyze first packet with Wireshark

## Scenario

In this scenario, you’re a security analyst investigating traffic to a website.

You’ll analyze a network packet capture file that contains traffic data related to a user connecting to an internet site. The ability to filter network traffic using packet sniffers to gather relevant information is an essential skill as a security analyst.

You must filter the data in order to:
* Identify the source and destination IP addresses involved in this web browsing session.
* Examine the protocols that are used when the user makes the connection to the website.
* Analyze some of the data packets to identify the type of information sent and received by the systems that connect to each other when the network data is captured.

For an overview of the key property columns listed for each packet:
* **No. :** The index number of the packet in this packet capture file
* **Time:** The timestamp of the packet
* **Source:** The source IP address
* **Destination:** The destination IP address
* **Protocol:** The protocol contained in the packet
* **Length:** The total length of the packet
* **Info:** Some information about the data in the packet (the payload) as interpreted by Wireshark

<br/>**1. Identify the source and destination IP addresses involved in the web browsing session**

* Enter the `ip.addr == 142.250.1.139` in the filter bar to filter for traffic associated with a specific IP address. This filter allows to see all network traffic that is directly involved with the host having the IP address `142.250.1.139`.

<img width="800" alt="AD_4nXemPlXLSD3rDr0CkFdUZlfVuoC0tE81Iw-ALb3SIO3P__B9pqHeFZCTfIxlJ5Z7ZLfE-b2W4LUeIWqLELH8zjDqJMMftyfwQgRdpT-4IVz3DUmi68w7tmKi" src="https://github.com/user-attachments/assets/f20e383b-d776-41eb-bf93-005c156d5600" /><br/>

![AD_4nXf5MBW-8Q_X3qyfWeTK-bVmkIktJIH39SoGnRVHcnc3bFf5AaVvSs-wXi3m-6NdOcyTPyiTZGyirx98WYcVh3uFI1aAVrvSmK4sWJwtgT4W5VTaELeV-vX1](https://github.com/user-attachments/assets/ffb1f661-e177-41fa-b4ee-8c6a2c6c7a01) <br/>

* Double-click the first packet that lists `TCP` as the protocol.
* The first subtree in the upper section starts with the word `Frame` which is a details about the overall network packet, or frame, including the frame length and the arrival time of the packet. It is information about the entire packet of data.
* The next subtree `Ethernet II`. This subtree contains details about the packet at the Ethernet level, including the source and destination MAC addresses and the type of internal protocol that the Ethernet packet contains.
* The subtree `Internet Protocol Version 4`. This third subtree label reflects the protocol. This shows packet data about the Internet Protocol (IP) data contained in the Ethernet packet. It contains information such as the source and destination IP addresses and the Internal Protocol (for example, TCP or UDP), which is carried inside the IP packet.
* The `Transmission Control Protocol (TCP)` subtree details TCP packet information like source/destination ports, sequence numbers, and `Flags`. `Flags` provide a detailed view of the TCP flags set in this packet. These ports match those seen in the main Wireshark window's summary display.<br/>

![AD_4nXf6ezJDILjRqbTXycbbXXDtHhFgjWVMNIKesiEE9wCoc_xvFkHRT_OMrWFsUntae2OmsQKzxCmNW4MwIHYbTr8qbKQ490xtcU9LZCROkggFO6DrPwNUoRPI](https://github.com/user-attachments/assets/1c9b4c13-3f38-430b-901c-1ab08115fb84)<br/>

* The `ip.src == 142.250.1.139` filter is to display traffic originating **only** from the specified source IP address `142.250.1.139`.

![AD_4nXedqJX5mvrQDqwccC72GWRzpGgu-klJhVuf1O1K3t7F_OGPEjJ7LvTLVUoeJCy8ZdyBmBpg9jzdIJmfehWpIcpL8Ne4vdrqFjz92rhvX_wiUPwo_ey6-1Yl](https://github.com/user-attachments/assets/ee2998f7-6515-4a57-a949-e9af6261c204)<br/>

* The `ip.dst == 142.250.1.139` filter is to view  traffic for a specific destination IP address only.

![AD_4nXfXKtXKYz0Mew9I6kbDLti7N0_3GvWrvDuGW2F2MzKPsf-tiXIKmb37kayZzBlJcyd6Lm6Teb6WYJw_7rlphIPoh3FAKF27Ed5f9Ed5os5tRS5vFkySDyFw](https://github.com/user-attachments/assets/4b557173-193e-4275-858a-175ed7655353)<br/>

* The following filter `eth.addr == 42:01:ac:15:e0:02` is to select traffic to or from a specific Ethernet MAC address. This filters traffic related to one MAC address, regardless of the other protocols involved: <br/>

![AD_4nXfxckytkNQTVXr6HRMdHQXe4HbhMnfzmAY5-F6r1X7RwkJnRV6LBefRNgoIK9Z6Eg0r9I5uqasPiNVC8fNchv3eK6GQVx-cpfBkb5WTDgQwubp4szEBEssm](https://github.com/user-attachments/assets/3427d424-556a-4497-8393-b7045bbe4d5c) <br/>

* Double-click the first packet in the list. The filter's MAC address is found as the source or destination within the `Ethernet II` details.
* Within the `Internet Protocol Version 4` subtree there are `Time to Live` and `Protocol` fields. The `Protocol` field indicates which IP internal protocol is contained in the packet. <br/>  

**2. Examine the protocols that are used when the user makes the connection to the website**

* Enter the `udp.port == 53` filter to select UDP port **53** traffic. `DNS` traffic uses UDP port `53`, so this will list traffic related to DNS queries and responses only.<br/>

![AD_4nXccRHr3pleMSn_rAwYuzhRqF20ssi6ze6YRmBgmsg7i6mh6bW3ttRUdmE5EwyLovS2yBHH3nel_FR9d5Tawl_I0a235aAaUwSL5ezFz8NSbvwCbqiPT1_Uk](https://github.com/user-attachments/assets/4e1b5d2f-9055-42e7-affb-ff4a2fa9c086) <br/>

* Double-click the first packet in the list. `The Queries` from the subtree `Domain Name System` provides the name of the website that was queried is `opensource.google.com`.
* The `Answers`, in the `Domain Name System (query)` subtree. It includes the name that was queried (opensource.google.com) and the addresses that are associated with that name. <br/>

**3. Analyze some of the data packets to identify the type of information sent and received by the systems that connect to each other when the network data is captured**

* Enter the `tcp.port == 80` filter to select TCP port `80` traffic. TCP port `80` is the default port that is associated with web traffic:

![AD_4nXc3Cs6lHHml7szRbHt9fDyI45s4RPB-oqnQLnUjRf3TA88T1Ef9Ihb3hCsJzrAgs3mbqQ8PF0ceGct3_xcMylY9WmzPaooRkn99LfvSBgCLJPCveEiBwe29](https://github.com/user-attachments/assets/bba508be-02ba-4c05-8741-841da9a2831a) <br/>

* Double-click the first packet in the list. The Destination IP address of this packet is `169.254.169.254` and the source is `172.21.224.2`. It will show information of the following fields:
  * The Time to Live value is **64**.
  * The Frame length is **54 bytes**.
  * The Header Length is **20 bytes**.

![AD_4nXfKI3J949TkRvZswRruhQ-QN7AlevVHsDpNoZ4TFw0Rkb7AIzPQ1poBwKzQvBJQLdvnse82m9OtaopuQ0LonAppl_vsnR-uqJ2Le7uQXaQaOJ5pP8-7jV-W](https://github.com/user-attachments/assets/052e464e-1f03-4862-a83e-55f88a0ccee9) <br/>

* The filter `tcp contains “curl”` is to **display filter** that shows all TCP packets that contain the `"curl"` command anywhere within this sample packet capture file.
* The `“curl”` filter is to identify curl activity: If you suspect someone is using the `curl` command-line tool (or any application that sends "curl" in its data) to fetch web pages, interact with APIs, or transfer data, this filter can help quickly spot those packets.




