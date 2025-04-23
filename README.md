<p align="center">
  <img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

# How to Create and Manage Groups and Users in Active Directory

This tutorial outlines how to create a Sales group within Active Directory and apply permissions to it by creating a security group.

## Environments and Technologies Used
- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services

## Operating Systems Used
- Windows Server 2022
- Windows 10 (21H2)

## High-Level Configuration Steps
- Create a Security Group called 'Sales'
- Add users to the 'Sales' Group
- Create a shared folder that can only be read and modified by members of the 'Sales Group'
- Demonstrate how non-sales users cannot access this file

## Deployment and Configuration Steps

### Creating a 'Sales' Group

1. Create an OU called 'Sales' in **Active Directory Users and Computers**. Right-click, select **New**, and choose **Group**. Name the group 'SalesGroup', set the scope to **Global**, and the type to **Security Groups**. Move 3 users from the _EMPLOYEES OU to the OU 'Sales'.
   <p align="center">
     <img src="https://imgur.com/PU5Tohl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   </p>
   <p align="center">
     <img src="https://imgur.com/Te34GwC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   </p>

2. Add the users from the 'Sales' OU to the SalesGroup. Right-click the SalesGroup, go to **Properties**, then **Members**, and select **Add** to add all members.
   <p align="center">
     <img src="https://imgur.com/zRlCRjA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   </p>
   <p align="center">
     <img src="https://imgur.com/13Moq7j.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   </p>

3. Next, create a file on the C Drive called 'Top-Secret'. Go back to the Sharing tab, click on Advanced Sharing, check share this folder, click permissions. Remove 'Everyone'. Click add and type in SalesGroup and Domain Admins. Click ok. Check 'full control' 
   <p align="center">
     <img src="https://imgur.com/k9FG1rv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   </p>

4. Create another OU called 'Marketing' along with a Security Group for the OU named 'MarketingGroup'. Add the fourth user to the Marketing OU and then add them to the 'MarketingGroup' security group.
   <p align="center">
     <img src="https://imgur.com/ZmiDAak.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   </p>

5. Test permissions to ensure they are successful by logging into `active-directory-client` as a member of the SalesGroup or a Domain Admin, then logging in as a member of 'MarketingGroup'.

