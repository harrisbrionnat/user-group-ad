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

3. Next, create a file on the C Drive called 'Top-Secret'. Go back to the Sharing tab, click on **Advanced Sharing**, check **Share this folder**, and click **Permissions**. Remove 'Everyone'. Click **Add** and type in `SalesGroup` and `Domain Admins`. Click **OK** and check **Full Control**.
   <p align="center">
     <img src="https://imgur.com/k9FG1rv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   </p>

4. Map the network drive on `active-directory-client`. Navigate to **File Explorer** → **This PC**. Right-click on **This PC**, go to **Map network drive**. Select a drive letter for the current PC and for the folder name put `\\servername\Top-Secret`.
   <p align="center">
     <img src="https://imgur.com/AIiYBGC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   </p>

5. Create another OU called 'Marketing' along with a Security Group for the OU named `MarketingGroup`. Add the fourth user to the `Marketing` OU and then add them to the `MarketingGroup` security group.
   <p align="center">
     <img src="https://imgur.com/IYOPXVY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   </p>

6. Test permissions to ensure they are successful by logging into `active-directory-client` as a member of the `SalesGroup` or a `Domain Admin`. Then log in as a member of `MarketingGroup`. You should be able to access the folder with no problems as a member of the `SalesGroup` or a `Domain Admin`. Access should be denied when attempting to map the drive using an account from `MarketingGroup`.
   <p align="center">
     <img src="https://imgur.com/3TW2frC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   </p>

