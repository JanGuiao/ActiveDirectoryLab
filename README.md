# Basic Home Lab Running Active Directory

Steps on how I setup a basic home lab running Active Directory

## Utilites
- PowerShell
- Virtual Box

## Environments
- Windows 10 ISO
- Server 2019 ISO

## Network Diagram

![DwXHjAi - Imgur](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/2fed9a10-0819-41fb-9031-7c1c8bcd578c)

## Download and install Oracle VirtualBox from the official website.

[Oracle Virtual Box](https://www.virtualbox.org/)

## Download the Windows 10 and Server 2019 ISO files.

[Windows 10 ISO](https://www.microsoft.com/en-us/software-download/windows10ISO)
[Windows Server 2019 ISO](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2019)

## Create a new Virtual Machine 
- Name: DC
- ISO: Attach **Server2019 ISO** downloaded previously
- OS: Windows 64-bit
- Hardware: <b>Based on your hardware compatibilities<b>
- Disk: Default
  
![Step 4](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/80a7e00b-ea94-4fba-b2a2-5d6f9b03097d)

Go into the newly made VM "DC" settings add "QUALITY OF LIFE" with Bidirectional Clipboard and Drag'n Drop (Optional). 

![Step 5](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/b43d1c88-bb91-454f-9dbf-f3735b2b14f1)

In the Network tab, enable Network Adapters (2) **NAT** & **INTERNAL NETWORK** 

![Step 6](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/ea17c253-3951-44cc-8286-0a867b671548)

![Step 7](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/840e3097-f898-4b2a-8a13-3c0ca7e6d46a)


##  Server 2019 Setup

- Windows Server 2019 Standard (Desktop Experience)
- Custom Drive
- Password: (Optional) 
  
![Step 8](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/1d0b6ddd-57ac-40d4-83ea-a5f3fd3b6124)

![Step 9](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/0cd8b08e-e141-409d-9eae-1e005a25b0f3)


## Windows / Server Manager Configuration

**See Diagram** 
- Internal (Adapter)

![Step 10](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/313d872a-c1e6-4733-aa67-67cc9d7a6134)
![Step 11](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/15182388-28d6-4e29-8b34-70a049162c31)

- Add Roles and Features Wizard (Server Manager)

Choose Active Directory Domain Services (when asked to add features - accept) and install features. 

![Step 12](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/0d18e9dc-335e-4a8d-ac0d-a14d2018b0df)

- After newly installed AD features, post-deployment configuration is needed. Proceed with promoting server to domain controller
In **Deployment Configuration** : Add a new forest ; DSRM password (!!ex:Password12345!! *for lab purposes*) ; View results and Install

![Step 13](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/1d10b913-4efc-4183-abae-81bd311d4f28)
![Step 14](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/cd24f419-b6e8-4840-b212-03eb9b31dccd)
![Step 15](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/8a5dc472-c009-4718-9213-995f5834e1ee)
![Step 16](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/a16679c0-b132-41c9-bf5d-91e7c87f2470)




##  Create Admins group in "Active Directory Users and Computers" and login as newly created admin.

![Step 18](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/5165d9c1-4745-4424-89e7-51831d73c926)
![Step 19](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/0b009a8a-9e48-4a03-88f4-58f50bc3bf7c)
![Step 20](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/3243d0a3-0809-46d0-ac49-a9e3ac73344b)
![Step 21](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/32a35d68-082d-4ff6-87c2-9d0cbae72ae7)
![Step 22](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/cf1360d9-e145-4328-8e08-144a98c5ca4f)
![Step 23](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/84a0da07-0ff2-4c74-921d-2f3d57982fe7)





##  Add Roles and Features "Routing and Remote Access"

- Under "Server Roles" choose **Remote Access** and add features.

![Step 25](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/95204a02-9441-469a-828c-4c20e9ab7512)

- Notice the DC Server is disconnected, right click the server and configure.
  
![Step 26](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/62b6a06b-2247-48b9-afe1-4a1eef31884d)
![Step 27](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/bd41227e-6775-464c-9832-8969a9c4a18b)

- Use default network interfaces publicly provided to connect to the Internet.
  
![Step 28](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/0a6f8e46-2dbf-49c2-846c-48f2d48d2ac3)

- If status is still down (red arrow), refresh.
  
![Step 29](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/65a36016-c130-424f-9876-5e87963334e4)








##  Add Roles and Features "DHCP Server" 

![Step 30](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/6be27a0b-7afc-40e1-a8b5-7ac3fd7f4ea1)
![Step 31](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/d827eed7-f2c7-4630-a8ff-71dbd66e9499)

- Configure IPv4 Scope IP Address Range *Refer to Diagram Example*
  
![Step 32](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/c74c5b77-9a57-493a-bee6-f0fcf1ef8723)

- Lease Duration *dependent on situation, choose 8 days as default for lab purposes*
  
![Step 33](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/60a9d046-7d82-4529-b080-933e5ca10e58)
![Step 34](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/d9b231cc-f7bd-4b87-99c4-645ac5143ba1)

- For Router (Default Gateway) configuration, add Internal IP Address (172.16.0.1) *Do not forget to click add to the entries*
![Step 35](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/58c6cbe6-337f-4b6e-bca2-a1a0bc0ee420)
![Step 36](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/99641b29-ee48-403a-8281-e563b610e081)

*If Server is down, refer to the main server "dc.jandomain.com" -> Authorize -> Refresh*

![Step 37](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/dad4e805-3ec9-4d96-a901-87bf45aa6bed)



##  Create and Generate users via PowerShell Script created by JoshMadakor [Power Shell script for creating users](https://github.com/joshmadakor1/AD_PS)
![Revise](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/83c42f7e-36c9-4165-b88b-a1fcda5d1911)


- Open PowerShell ISE, under File -> Open the file for the script *ExecutionPolicy must be set "unrestricted" (for lab purposes only)*

![Step 39](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/347ea049-81b2-4923-8c86-d065daa16806)

- Change directory to where script is located
  
![Step 40](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/6f9095c9-aa56-4389-a930-e3b8675fae63)

- Run Script
  
![Step 41](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/af705746-54ec-44f3-b790-5916c546d664)

-After script is finished, look for users in "Active Directory Users and Computers" tool. 

![Step 42](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/66a1553a-c42d-4771-a77a-5fde88c6a045)
![Step 43](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/08eb149c-b56a-4afe-89a7-57bd8e192485)

##  Create new VM Windows 10 (CLIENT) 
- Name: CLIENT
- ISO: Windows 10 ISO
- OS: Windows 10 (64-bit)
- Hardware: <b>Based on your hardware compatibilities<b>
- Disk: Default

![Step 44](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/70397411-cdd7-4f20-a73e-46293e399e6a)

- Configure CLIENT Settings
Under Network tab, "Enable Network Adapter" to be attached to **Internal Network**

![Step 45](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/e67a1ce4-38e5-49c1-be54-2b2386e42c82)

- Run the CLIENT VM & complete Windows Setup

##  Ping Connectivity

- Run CMD (Command Prompt) as Admin -> run ipconfig command -> ping google.com (established connection) 
![Step 46 5](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/5e5462d0-d034-4b22-9531-3ec551c847f9)

- Ping your domain "jandomain.com"

![Step 46 5 pt2](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/78323b34-5faf-4b62-bb98-8ae469ddcee0)

## Associate CLIENT user with jandomain.com

-Make CLIENT user a member of "jandomain.com" via "About Settings" under "Rename This PC (Advanced)" *Scroll down for advanced options*

![Step 47](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/5e25f631-8fe4-4e07-82b9-b1c10278edfc)

-Head back to previous DC Virtual Machine and check DHCP tools for validation of new CLIENT user address lease. 

![Step 48](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/7967dbeb-6c4e-44a9-93d4-035cdb19c7f9)

- CLIENT user viewable in "Active Directory Users and Computers"
![Step 49](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/f294cfea-b146-47b6-8d51-6962a8dae878)



##  Login as one of the generated users made in Active Directory (ex: Anton Simmons aka asimmons) 
![Step 50](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/bb8ec9e0-4321-42ce-a411-b532598c6b51)

- Run CMD show user via whoami
![Step 51](https://github.com/JanGuiao/ActiveDirectoryLab/assets/95273542/a622b8c6-0e4c-4501-ab8f-27bd7a7bfd46)






