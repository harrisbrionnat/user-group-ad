<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>How to Create and Manage Groups and Users in Active Directory</h1>
This tutorial outlines how one would create a Sales group within Active Directory and apply permissions to it by creating a security group.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services


<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Configuration Steps</h2>

- Create a Security Group called 'Sales'
- Add users to the 'Sales' Group
- Create a shared folder that can only be read and modified by members of the 'Sales Group'
- Demonstrate how non-sales users cannot access this file

  <h2>Deployment and Configuration Steps</h2>


<p>
  <h3
    ><b> Creating a 'Sales' Group</b>
  </h3>
  <br>
  <br>
1. Create an OU called 'Sales' in <b>Active Directory Users and Computers<b/>. Right click and click 'New' and choose 'Group'. Call the groups 'SalesGroup'. The scope will be 'Global and the type will be 'Security Groups'. Add some users to the OU 'Sales'.
   <p>
<img src="https://imgur.com/PU5Tohl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
     <p>
<img src="https://imgur.com/Te34GwC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
  <br>
  <br>
2. Add the users from the 'Sales' OU to the SalesGroup group. Right-click the SalesGroup. Go to <b>Properties</b> then <b>Members</b>, then <b>Add</b>. Add all of the members.
  <p>
<img src="https://imgur.com/zRlCRjA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
   <p>
<img src="https://imgur.com/13Moq7j.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
  <br>
  <br>
3. Next Create a file on the C Drive called 'Top-Secret'. Right-click the file. Go to <b>Properties</b> --> <b>Security</b>--><b>Advanced</b>--><b>Disable Inheritance</b>-->. Then click 'disable all inherited permissions'. Then go back to the security tab, click 'Edit', 'Add' and then enter 'SalesGroup.
  <br>
    <p>
<img src="https://imgur.com/qz4s1F9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
  <br>
4. Set the Domain Controller's NIC's Private IP address to static. Go to the Virtual Machines tab, click on active-directory-dc, <b>Networking</b> --> <b>Network Settings</b>. Click on the virtual NIC in the upper middle of the screen. Click <b>ip-config1</b>. Change to private ip setting from dynamic to static
  <br>
  <br>
5. For testing purposes, we will disable to Windows Firewall on active-directory-dc. Once logged into the vm, go to the Windows Firewall by right clicking the start menu and clicking <b>Run</b>. Type wf.msc. Click <b>Windows Defender Firewall Properties</b>. Turn the firewall state to 'off' for the Domain, Private, and Public Profile tabs.
</p>

<br />

<p>
