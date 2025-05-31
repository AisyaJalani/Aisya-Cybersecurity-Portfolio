# Cybersecurity Incident Report : Analyze Network Attacks

## Scenario

You work as a security analyst for a travel agency that advertises sales and promotions on the company’s website. The employees of the company regularly access the company’s sales webpage to search for vacation packages their customers might like. 

One afternoon, you receive an automated alert from your monitoring system indicating a problem with the web server. You attempt to visit the company’s website, but you receive a connection timeout error message in your browser.

You use a packet sniffer to capture data packets in transit to and from the web server. You notice a large number of TCP SYN requests coming from an unfamiliar IP address. The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. You suspect the server is under attack by a malicious actor. 

You take the server offline temporarily so that the machine can recover and return to a normal operating status. You also configure the company’s firewall to block the IP address that was sending the abnormal number of SYN requests. You know that your IP blocking solution won’t last long, as an attacker can spoof other IP addresses to get around this block. You need to alert your manager about this problem quickly and discuss the next steps to stop this attacker and prevent this problem from happening again. You will need to be prepared to tell your boss about the type of attack you discovered and how it was affecting the web server and employees.

## Identify the type of attack that may have caused this network interruption

* One potential explanation for the website's connection timeout error message is: a DoS attack.
* The log show that: The web server stops responding after it is overloaded with the SYN packet requests.
* This event could be: SYN flooding which is a DoS attack.

## Explain how the attack is causing the website to malfunction

When website visitors try to establish a connection with the web server, a three-way handshake occurs using the TCP protocol. Explain the three steps of the handshake:

* A SYN packet is sent from the source destination, request for a connection.
* The destination replies with a SYN-ACK packet that accept the connection request.
* ACK packet is sent from the client to acknowledging the permission to connect.

Explain what happen when a malicious actor sends a large number of SYN packets all at once:
It disturbs the server's resources available for the connection and resulted with no server resources left for legitimate TCP connection requests.

Explain what the logs indicate and how that affects the server: The logs indicate that the web server slows down and unable to process the visitor's SYN requests. The server was unable to open available connection to new visitors which resulted to receive a connection timeout messages.



