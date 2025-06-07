# Capture first packet with Tcpdump

## Scenario  

You’re a network analyst who needs to use tcpdump to capture and analyze live network traffic from a Linux virtual machine.
The lab starts with your user account, called analyst, already logged in to a Linux terminal.
Your Linux user's home directory contains a sample packet capture file that you will use at the end of the lab to answer a few questions about the network traffic that it contains.

  You must filter the data in order to:
    * Identify network interfaces,
    * Use the tcpdump command to capture network data for inspection,
    * Interpret the information that tcpdump outputs regarding a packet, and
    * Save and load packet data for later analysis.


**1. Identify network interfaces**

  * The `ifconfig` used to identify the interfaces that are available. The Ethernet network interface is identified by the entry with the `eth` prefix.
  * The `tcpdump -D` used to identify the interface options available for packet capture. This also allows us to identify which network interfaces are available.

    
