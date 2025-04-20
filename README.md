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
3. Next Create a file on the C Drive called 'Top-Secret'. Right-click the file. Go to <b>Properties</b> --> <b>Security</b>--><b>Advanced</b>--><b>Disable Inheritance</b>-->. Then click 'disable all inherited permissions'. Then go back to the security tab, click 'Edit', 'Add' and then enter 'SalesGroup. Add a .txt file to the 'Top-Secret' folder.
  <br>
    <p>
<img src="https://imgur.com/qz4s1F9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
  <br>
4. Create another OU called 'Marketing' along with a Security Group for the OU called 'MarketingGroup'. Create a user in the Marketing OU and add them to the 'MarketingGroup' security group.
  <br>
    <p>
<img src="https://imgur.com/ZmiDAak.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
  <br>
5. Test permissions are successful by logging into active-directory-client as a member of the SalesGroup and then logging in as a member of 'MarketingGroup'.
</p>

<br />

<p>
