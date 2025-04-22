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

1. Create an OU called 'Sales' in **Active Directory Users and Computers**. Right-click, select **New**, and choose **Group**. Name the group 'SalesGroup', set the scope to **Global**, and the type to **Security Groups**. Add users to the OU 'Sales'.
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

3. Next, create a file on the C Drive called 'Top-Secret'. Right-click the file and go to **Properties** → **Security** → **Advanced** → **Disable Inheritance**. Choose to disable all inherited permissions. Go back to the security tab, click **Edit**, **Add**, and enter 'SalesGroup'. Add a `.txt` file to the 'Top-Secret' folder.
   <p align="center">
     <img src="https://imgur.com/qz4s1F9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   </p>

4. Create another OU called 'Marketing' along with a Security Group for the OU named 'MarketingGroup'. Create a user in the Marketing OU and add them to the 'MarketingGroup' security group.
   <p align="center">
     <img src="https://imgur.com/ZmiDAak.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   </p>

5. Test permissions to ensure they are successful by logging into `active-directory-client` as a member of the SalesGroup, then logging in as a member of 'MarketingGroup'.

