<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Building Domain Name System Intuition in Active Directory</h1>
This tutorial will help build general intuition and understanding of how Domain Name Systems (DNS) work in the Active Directory Environment<br />

<h2>Prerequisites</h2>
Configure an on-premises Active Directory within Azure VMs using my previous project as a reference --> https://github.com/BrianRivera22/configure_AD/blob/main/README.md

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

1) A-Record Exercise

2) Local DNS Cache Exercise

3) CNAME Record Exercise


<h2>Deployment and Configuration Steps</h2>

<h4>1. A-Record Exercise</h4>
<p>
<img src="https://github.com/BrianRivera22/DNS_Intuition/blob/main/Building%20DNS%20Intuition/1.png"/>
</p>
<p>
Log into client-1 as jane_admin and ping "mainframe" within PowerShell.

Notice that the request cannot be completed. Type "nslookup mainframe" and notice that the DNS cannot resolve this name to an IP address.

<p>
<img src="https://github.com/BrianRivera22/DNS_Intuition/blob/main/Building%20DNS%20Intuition/2.png"/>
</p>
<p>
Within dc-1 login as jane_admin and open up DNS Manager. Navigate to mydomain.com and right click to create a New Host A-Record

Type in "mainframe" and have the record resolve it to the domain controller server's IP address. I used command ipconfig in PowerShell to find the IP address.

<p>
<img src="https://github.com/BrianRivera22/DNS_Intuition/blob/main/Building%20DNS%20Intuition/3.png"/>
</p>
<p>
In PowerShell if we ping "mainframe" we will notice the IP address that it pings.

<h4>2) Local DNS Cache Exercise</h4>
<p>
<img src="https://github.com/BrianRivera22/DNS_Intuition/blob/main/Building%20DNS%20Intuition/4.png"/>
</p>
<p>
Back within DNS manager, change the IP address to 8.8.8.8

<p>
<img src="https://github.com/BrianRivera22/DNS_Intuition/blob/main/Building%20DNS%20Intuition/5.png"/>
</p>
<p>
Ping "mainframe" again in PowerShell and notice that it still pings 10.0.0.4

This is due to the DNS cache still having mainframe as 10.0.0.4

<p>
<img src="https://github.com/BrianRivera22/DNS_Intuition/blob/main/Building%20DNS%20Intuition/6.png"/>
</p>
<p>
In PowerShell type "ipconfig /displaydns" to see the DNS cache still has 10.0.0.4 for mainframe

<p>
<img src="https://github.com/BrianRivera22/DNS_Intuition/blob/main/Building%20DNS%20Intuition/7.png"/>
</p>
<p>
Type "ipconfig /flushdns" and then "ipconfig /dnsdisplay". This will let us see the emptied DNS cache.

<h4>3) CNAME Record Exercise</h4>
<p>
<img src="https://github.com/BrianRivera22/DNS_Intuition/blob/main/Building%20DNS%20Intuition/8.png"/>
</p>
<p>
Within DNS manager add a new CNAME. Use "search" and link it to google.com

<p>
<img src="https://github.com/BrianRivera22/DNS_Intuition/blob/main/Building%20DNS%20Intuition/9.png"/>
</p>
<p>
Within PowerShell enter "nslookup search" and notice that it looks up google.com's IP address.

This concludes the tutorial!

