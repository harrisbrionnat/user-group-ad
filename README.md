<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>How to Install and Deploy Active Directory in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services


<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Within Azure, create a Windows 10 and Windows Server 2020 virtual machine
- Enable Active Directory Domain Services on the Windows Server virtual machine
- Join the Windows 10 client machine to the Domain Controller on the Windows Server virtual machine
- Allow non-administrative users to access remote desktop
