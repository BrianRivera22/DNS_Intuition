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

1) Setup an Account Lockout within your Active Directory Infrastructure   
    - Configure Account Lockout Threshold in Group Policy
    - Lock yourself out of a user account to ensure the policy works (fun!)
2) Enable and Disable Accounts
    - unlock user account
    - observe ability to enable, disable, and reset passwords for users within Active Directory Users & Computers
3) Observe Logs within Event Viewer
    - Observe the logs on the client Machine


<h2>Deployment and Configuration Steps</h2>

<h4>1. </h4>
<p>
<img src=""/>
</p>
<p>
word

