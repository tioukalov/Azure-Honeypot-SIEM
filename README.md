<h1 align="center">Azure Honeypot SIEM</h1>
We will use Microsoft Azure Sentinel (SIEM) to expose a virtual computer to the public and gather threat actors’ geographical information based on their failed Windows remote desktop attempts. 
<h3>Environments and Technologies Used</h3>

- PowerShell ISE
- Microsoft Azure: Log Analytics Workspace
- Microsoft Azure: Sentinel


<h3>Operating Systems Used</h3>

- Windows 10 Pro


<h2>Deployment and Configuration Steps</h2>
<p>Create a VM with an inbound security rule that allows all traffic into the computer.</p>
<p>Under Microsoft Defender, we allow all security events to be stored in Azure</p>
<p>Go to the virtual machine’s Windows firewall and turn the firewall state off</p>
<p>Construct a script that pulls failed RDP logons on Windows Event Viewer: Event ID 4625. The IP address is then sent to a third-party API called ipgeolocation that outputs the threat actors’ geo data.</p>
<p>The raw data from the logs are then parsed to add structure.</p>
<p>The latitude and longitude are plotted on a visual map.</p>
<p>After a few hours, we reached the API’s max free requests  </p>
