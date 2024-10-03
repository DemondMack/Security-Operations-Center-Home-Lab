<h1>Security Operations Center Home Lab</h1>


<h2>Description</h2>
This project consists of setting up a fully functioning cloud-based SOC environment, using ELK as the SIEM and implementing osTicket for ticketing. I monitored network traffic, simulated attacks to test incident response processes, and responded to alerts generated.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Elasticsearch</b>
- <b>Kibana</b>
- <b>osTicket</b>
- <b>Mythic</b> (C2 Framework)

<h2>Environments Used </h2>

- <b>Vultr Cloud</b>
- <b>Kali Linux</b>
- <b>Ubuntu</b>
- <b>Windows</b>

<h2>Project walk-through:</h2>

<p align="center">
VPN Network Diagram: <br/>
<img src="https://i.imgur.com/9bgnKz0.jpeg" height="80%" width="80%" alt="Virtual Private Network Diagram"/>
          <p>   Created a network diagram to show the virtual private network and the connections within the network</p>  
<br />
<br />
External Connections to VPN:  <br/>
<img src="https://i.imgur.com/fK9H4qp.jpeg" height="80%" width="80%" alt="External Connections to VPN"/>
<p> Created a diagram to show external devices and servers connecting to the vpn</p>
<br />
<br />
<br />
Ubuntu VM deployed with Elasticsearch: <br/>
<img src="https://i.imgur.com/pvVYyv2.jpeg" height="80%" width="80%" alt="VPC w/ Ubuntu VM "/>
<p>In this stage, I created a Virtual Private Cloud (VPC) in Vultr, deployed an Ubuntu virtual machine, and installed Elasticsearch to serve as part of the ELK Stack. After configuring the Elasticsearch settings for external access, I implemented firewall rules to restrict access to the machine, ensuring only authorized connections. Finally, I started the Elasticsearch service and verified that it was running successfully.</p>
<br />
<br />
<br />
Kibana installation & setup:  <br/>
<img src="https://i.imgur.com/pioyqbu.jpeg" height="80%" width="80%" />
<img src="https://i.imgur.com/yh4XEe9.jpeg" height="80%" width="80%" />
<p>Downloaded and installed Kibana on the existing Ubuntu virtual machine, then configured Kibana by updating the server port and host in its configuration file. Enabled and started Kibana as a service. Generated an Elasticsearch enrollment token and used it to connect Kibana to Elasticsearch. Adjusted firewall rules to allow access to port 5601, then logged into Kibana successfully. Finally, configured encryption keys for Kibana to ensure persistent settings for saved objects and security.</p>
<br />
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
