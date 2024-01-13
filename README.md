<h1 align="center">Azure Honeypot SIEM</h1>
<p align="center"><img src="https://i.imgur.com/J2Ts1xi.png" height="35%" width="35%" alt="SIEM image"/></p>
We will use Microsoft Azure Sentinel (SIEM) to expose a virtual computer to the public and gather threat actors’ geographical information based on their failed Windows remote desktop attempts. 
<h3>Environments and Technologies Used</h3>

- PowerShell ISE
- Microsoft Azure: Log Analytics Workspace
- Microsoft Azure: Sentinel


<h3>Operating Systems Used</h3>

- Windows 10 Pro


<h2>Deployment and Configuration Steps</h2>
<p><img src="https://i.imgur.com/O9ifnIw.png" height="40%" width="40%" alt="diagram"/></p>

- Create a VM with an inbound security rule that allows all traffic into the computer.
- Under Microsoft Defender, we allow all security events to be stored in Azure
- Go to the virtual machine’s Windows firewall and turn the firewall state off
  
<p><img src="https://i.imgur.com/MsH3xk5.png" height="100%" width="100%" alt="turned off firewall"/></p>  

- Construct a script that pulls failed RDP logons on Windows Event Viewer: Event ID 4625. The IP address is then sent to a third-party API called ipgeolocation that outputs the threat actors’ geo data.
- The raw data from the logs are then parsed to add structure.

<p><img src="https://i.imgur.com/lut5nBN.png" height="100%" width="100%" alt="Raw Data parsed"/></p>  
  
- The latitude and longitude are plotted on a visual map.
- After a few hours, we reached the API’s max free requests. Below is a screenshot of the world map with all the failed RDP logons.

<p><img src="https://i.imgur.com/UBlGbM0.png" height="100%" width="100%" alt="SIEM map"/></p>

Thank you for your time.
