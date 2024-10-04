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
Windows Server seperated from VPC:  <br/>
<img src="https://i.imgur.com/o2grXTy.jpeg" height="80%" width="80%" />
<p>Deployed a Windows Server 2022 on Vultr using the shared CPU option. The server was set up without being part of the Virtual Private Cloud (VPC) to isolate it from other critical infrastructure. Configured the server and verified Remote Desktop Protocol (RDP) access to ensure it's exposed to the internet. The server will start generating logs for future analysis of unsuccessful login attempts.</p>
<br />
<br />
<br />
Fleet Server with Elastic Agent and Windows Server enrolled:  <br/>
<img src="https://i.imgur.com/uXz0c3B.jpeg" height="80%" width="80%" />
<img src="https://i.imgur.com/ypcURGK.jpeg" height="80%" width="80%" />
<img src="https://i.imgur.com/T5iRfce.jpeg" height="80%" width="80%" />
<p>Deployed an Ubuntu server to act as the Fleet Server in the cloud and configured it to manage agents centrally. Installed and configured the Elastic Agent on the Fleet Server and addressed connection issues by adjusting firewall rules for both the Fleet Server and Elasticsearch (port 9200 and 8220). Successfully enrolled the Windows Server into the Fleet, allowing for system logs and metrics collection. Finally, captured initial authentication logs from the Windows server, verifying the setup.</p>




<br />
<br />
Sysmon installation:  <br/>
<img src="https://i.imgur.com/MlnUpcj.jpeg" height="80%" width="80%" />
<img src="https://i.imgur.com/KcM0yLC.jpeg" height="80%" width="80%" />
<img src="https://i.imgur.com/NLHMqsW.jpeg" height="80%" width="80%" />
<p>Installed and configured Sysmon on the Windows Server. Downloaded Sysmon from Microsoft Learn and retrieved a popular configuration file from GitHub. Using PowerShell, installed Sysmon as a service and confirmed its successful setup by checking the Windows Event Viewer for Sysmon logs. Verified that Sysmon was capturing network connections and generating logs for further monitoring.</p>
<br />
<br />
<br />
Intergrated Sysmon & Microsoft Defender:  <br/>
<img src="https://i.imgur.com/9FOaHUI.jpeg" height="80%" width="80%" />
<img src="https://i.imgur.com/rOaZ4Js.jpeg" height="80%" width="80%" />
<p>Added integrations for Sysmon and Microsoft Defender into the Elasticsearch instance, allowing the collection of logs from custom Windows Event channels. Configured specific event IDs for ingestion, such as 1116, 1117, and 50001, for more targeted logging. Troubleshooting included ensuring connectivity between agents and Elasticsearch by allowing incoming connections on port 9200. Verified Sysmon and Defender logs were successfully ingested into the instance.</p>


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
