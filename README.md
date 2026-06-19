# My Windows Active Directory 2022 Homelab
<br>

## What is this?
>This is a collection of documentation from my recent Active Directory Homelab involving Windows Server 2022
## What's the point?
>The point of this lab is to gain hands on experience in working with Active Directory in a business environment. I believe true understanding is only ever achieved when you are able to explain the subject to another person with no experience, so this lab will follow more of a 'How to' style format.
## What was used?
> This lab was completed using a Desktop PC running a 14th Gen Intel Core i5 Processor, 16GB of DDR5 RAM, and a NVIDIA RTX 4060 8GB Graphics Card. The software used was VMware Workstation Pro provided by Broadcom, the Operating Systems include Windows Server 2022 Standard, and Windows 11 Pro.
> 16GB of Memory is recommended at minimum as we will be allocating 10GB of Memory soley to Virtualization to meet minimum requirements.
##
<br><br>

# PART A:  Setting up the Windows 11 Pro Client Machines
<br>

# Step 1
>Download, Install, and Run VMware Workstation Pro
<img width="973" height="547" alt="image" src="https://github.com/user-attachments/assets/f09d8014-fe5b-4e37-bb0e-9c52a0de9053" />

# Step 2
>Create the first Windows 11 Pro Client Virtual Machine, Select "Typical" install, then click next.
<img width="2559" height="1439" alt="Screenshot 2026-06-17 194224" src="https://github.com/user-attachments/assets/9ef0ed3b-36d6-4860-8741-8259391891a8" />

# Step 3
>Select the " Installer disc image file (iso) " option and navigate to the location where you downloaded your Windows 11 ISO, then click next.
<img width="2559" height="1439" alt="Screenshot 2026-06-17 194229" src="https://github.com/user-attachments/assets/b080978b-6cda-4c61-b6f3-c528b62f99e5" />

# Step 4
>Name the Virtual Machine to something memorable such as Win11_Client_1, then click next.
<img width="2559" height="1439" alt="Screenshot 2026-06-17 194258" src="https://github.com/user-attachments/assets/c2c8f1c0-3519-4c2b-8d6e-bf178cea1553" />

# Step 5
>Select "Only the files needed to support a virtual TPM", and then generate a secure password or create one manually.
<img width="2556" height="1439" alt="Screenshot 2026-06-17 194326" src="https://github.com/user-attachments/assets/539c4fa5-0133-4aeb-a978-0cd79d1c5d4b" />

# Step 6
>Allocate a minimum of 64GB of Storage capacity to meet the Windows 11 hardware requirement for installation. Leave the rest of the settings as default, then click next.
<img width="2550" height="1439" alt="Screenshot 2026-06-17 194332" src="https://github.com/user-attachments/assets/e92ec182-902b-4dcc-a98a-58f2945c6e1b" />

# Step 7
>Review your Virtual Machine Configuration, then finally click finish.
<img width="2559" height="1439" alt="Screenshot 2026-06-17 194343" src="https://github.com/user-attachments/assets/f57dbecc-5083-4f43-8310-4f95a2dc7d00" />
<img width="2559" height="1439" alt="Screenshot 2026-06-17 194352" src="https://github.com/user-attachments/assets/36964bf7-62e3-43b9-aebc-ee06a949e5d9" />

# Step 8
>Setup your Language and Time/Currency Format, then click next.
<img width="2559" height="1439" alt="Screenshot 2026-06-17 194415" src="https://github.com/user-attachments/assets/2b199a6b-e57a-4006-9ea9-7ff24224fa70" />

# Step 9
>Scroll down and select Windows 11 Pro, this is critical because the Home edition does not support joining a Domain, then click next.
<img width="2559" height="1439" alt="Screenshot 2026-06-17 194438" src="https://github.com/user-attachments/assets/0758b4c8-339c-4025-bb2a-de78aab3d48e" />

# Step 10
>Wait 10,000 years for Windows to install.
<img width="2559" height="1439" alt="Screenshot 2026-06-17 194503" src="https://github.com/user-attachments/assets/c252f8d7-7b1f-4e35-9924-574361d38c9b" />
<img width="2559" height="1439" alt="Screenshot 2026-06-17 195124" src="https://github.com/user-attachments/assets/ecd20f3c-00a4-4324-a3e9-bfbbb465ca05" />

# Step 11
>Select your Region
<img width="2559" height="1439" alt="Screenshot 2026-06-17 195202" src="https://github.com/user-attachments/assets/d28c432f-2e0e-480d-a33a-e762ca5fa954" />

# Step 12
>Name your client something memorable that is easily identifiable.
<img width="2559" height="1439" alt="Screenshot 2026-06-17 200745" src="https://github.com/user-attachments/assets/c016d6b8-0643-430c-ad2e-6c503f01262f" />

# Step 13
> Click the "Install Tools" button on the bottem right corner of the window to install needed drivers. 
<img width="2555" height="1439" alt="Screenshot 2026-06-17 201211" src="https://github.com/user-attachments/assets/2dd277eb-d692-48f1-9c93-13406e8a18df" />

# Step 14
> Grant the "VMware installation launcher" administrator privaliges 
<img width="2558" height="1439" alt="Screenshot 2026-06-17 201234" src="https://github.com/user-attachments/assets/9b08a4d7-5c0f-438c-bc9f-e27980438b81" />

# Step 15
> Navigate to the newly mounted DVD Drive labeled VMware Tools in File Explorer, and run the setup.exe file to launch the setup wizard, then click next.
<img width="2559" height="1439" alt="Screenshot 2026-06-17 201303" src="https://github.com/user-attachments/assets/f8bec305-8707-44d1-988e-85b711d11c8f" />

# Step 16
> Allow the installer to run, then click finish.
<img width="2559" height="1439" alt="Screenshot 2026-06-17 201442" src="https://github.com/user-attachments/assets/2fa82f5d-e16d-4fbf-abdd-039d0e67e0ef" />

# Step 17
> Power off the machine. You are done configuring the cline, at this point you may either repeat PART A or clone the Virtual Machine.
<img width="2559" height="1439" alt="Screenshot 2026-06-17 202000" src="https://github.com/user-attachments/assets/4afdc765-b406-4774-943c-7b16dbe0613f" />
<br><br>

# PART B: Setting up the Server VM 
<br>

# Step 1
> Begin by creating a new VM under File > New Virtual Machine, select custom Install.
<img width="2560" height="1440" alt="Screenshot (150)" src="https://github.com/user-attachments/assets/300fb366-cf2e-4bd0-aabe-a68a7867f3d0" />

# Step 2
> Select releavent hardware compatibility, the default is fine, then click next.
<img width="2560" height="1440" alt="Screenshot (151)" src="https://github.com/user-attachments/assets/d7932d1e-a9ed-457f-9bd2-7a3f40792dd8" />

# Step 3
> Select the "Installer disc image file (iso)" option and then navigate to where you downloaded your Windows Server 2022 ISO.
<img width="2560" height="1440" alt="Screenshot (152)" src="https://github.com/user-attachments/assets/24538a91-682c-4620-bc97-2c2efd25fc04" />

# Step 4
> Enter a product key if you have one, otherwise leave everything blank and click next.
<img width="2559" height="1439" alt="Screenshot 2026-06-18 111439" src="https://github.com/user-attachments/assets/03cca8b2-1b13-4986-82f8-e21ab853953d" />

# Step 5
> Name your Virtual Machine something memoraiable such as, "Windows_Server_2022", then click next.
<img width="2559" height="1439" alt="Screenshot 2026-06-18 111449" src="https://github.com/user-attachments/assets/2a014404-ae06-49fa-ba1a-2e37e7c161bb" />

# Step 6
> Ensure to select UEFI bootloader alonng with enabling Secure Boot, then click next.
<img width="2559" height="1439" alt="Screenshot 2026-06-18 111508" src="https://github.com/user-attachments/assets/60ef8dd6-3ed8-489f-96ec-afa11821d410" />

# Step 7
> Allocate a pre-detirmined amount of processing power for the VM to utilize. Two cores is recomended for stable performance, though 1 may work. Then click next.
<img width="2559" height="1439" alt="Screenshot 2026-06-18 111515" src="https://github.com/user-attachments/assets/06d87a05-75a1-4563-9575-18a7a0d003ad" />

# Step 8
> Specify how much memory you would like to allocate to the VM. (2GB is the minimum for the Standard Windows 2022 Server w/ Desktop Experience) then click next.
<img width="2559" height="1439" alt="Screenshot 2026-06-18 111522" src="https://github.com/user-attachments/assets/d9bff466-6808-46d7-8c54-6d2218e15fe2" />

# Step 9
> Select "Use network address translation (NAT)" for now to have basic internet access before we create a LAN segment later on.
<img width="2559" height="1439" alt="Screenshot 2026-06-18 111533" src="https://github.com/user-attachments/assets/825c3080-7264-47dd-b362-e7304bd039fb" />

# Step 10
> Leave this page as default, then click next.
<img width="2560" height="1440" alt="Screenshot (153)" src="https://github.com/user-attachments/assets/5008804a-cb21-47f3-809c-27878ef0ea9f" />

# Step 11
> Leave this page as default or select what is recommended for your OS, then click next.
<img width="2560" height="1440" alt="Screenshot (154)" src="https://github.com/user-attachments/assets/99af8702-86fb-431c-aca2-538c49720a4c" />

# Step 12
> Select, "Create a new virtual disk" and then click next.
<img width="2560" height="1440" alt="Screenshot (155)" src="https://github.com/user-attachments/assets/539cdba5-3ba2-4f83-8cfe-48c5a3b067e2" />

# Step 13
> Leave the Maximum disk size as whatever is recommended, then click next.
<img width="2560" height="1440" alt="Screenshot (156)" src="https://github.com/user-attachments/assets/98a18ed9-f355-44f7-90dd-c4d468a28cdf" />

# Step 14
> Name this disc file if you would like to, then click next.
<img width="2560" height="1440" alt="Screenshot (158)" src="https://github.com/user-attachments/assets/fbdd3c6e-e570-4124-9d27-d3c83c669d1c" />

# Step 15
> Review your Virtual Machine configuration, then click finish.
<img width="2560" height="1440" alt="Screenshot (159)" src="https://github.com/user-attachments/assets/3ce40fec-699e-4972-b9a5-278270983487" />

# Step 16
> Upon first boot, you will encounter a popup blocking you from continuing your install. Power off the machine.
<img width="2559" height="1439" alt="Screenshot 2026-06-18 111815" src="https://github.com/user-attachments/assets/cda24879-d862-43df-8b73-88690c30781c" />

# Step 17
> Navigate to the Virtual Machine settings under the VM tab, or hit (Ctrl + N)
<img width="2560" height="1440" alt="Screenshot (1)" src="https://github.com/user-attachments/assets/30af65c1-4670-48ab-8aa7-b039633858e0" />

# Step 18
> Click on the Floppy icon under Device.
<img width="2560" height="1440" alt="Screenshot (4)" src="https://github.com/user-attachments/assets/ac938744-2e8a-41af-9835-6a47bc23c8b7" />

# Step 19
> Disable "Connect at power on" under device status, then click ok, and finally power on the machine.
<img width="2560" height="1440" alt="Screenshot (5)" src="https://github.com/user-attachments/assets/9ac4eaea-c756-4190-9641-c280a4773599" />

# Step 20
> Select appropriate Language and Format settings, then click next.
<img width="2559" height="1439" alt="Screenshot 2026-06-18 112338" src="https://github.com/user-attachments/assets/d22f3020-44bf-4be6-bc75-91fc38b45874" />

# Step 21
> Click Install Now.
<img width="2559" height="1439" alt="Screenshot 2026-06-18 112345" src="https://github.com/user-attachments/assets/0ca4c71d-a6fb-4beb-af46-e74a5dbfacbc" />

# Step 22
> Select "Windows Server 2022 Standard Evaluation (Desktop Experience) 64-bit", then click next.
<img width="2559" height="1439" alt="Screenshot 2026-06-18 112421" src="https://github.com/user-attachments/assets/dca66ea5-d102-4e0b-bcb8-4dd082603c64" />

# Step 23
> Fully read and agree to the EULA, then click next.
<img width="2560" height="1440" alt="Screenshot (7)" src="https://github.com/user-attachments/assets/b497c653-2896-4280-98b4-5fdb734c6f39" />

# Step 24
> Select Custom Install.
<img width="2560" height="1440" alt="Screenshot (8)" src="https://github.com/user-attachments/assets/a18f7a2f-e82e-422f-8828-fdc8d323b3e5" />

# Step 25
> Select the designated install drive, then click next and wait for the installation process to complete.
<img width="2560" height="1440" alt="Screenshot (9)" src="https://github.com/user-attachments/assets/8572aee6-d063-4398-8449-ea5c0978f4a3" />

# Step 26
> Enter a strong password, then click finish.
<img width="2557" height="1439" alt="Screenshot 2026-06-18 112732" src="https://github.com/user-attachments/assets/bd7aa9cf-ed6d-4315-941e-fe85d223680d" />

# Step 27
> Login with the password you just created, you will automatically be lead to the Server Manager page to configure your Server. Allow the PC to be discoverable on the network, if this option does not come up by default it means VMware did't attatch a network adapter on boot, you can attatch it under VM > Removeable Devices > Network Adapter > Connect.
<img width="2560" height="1440" alt="Screenshot (49)" src="https://github.com/user-attachments/assets/ab376349-4fe1-48a6-8177-1acc5bce3b22" />

# Step 28
> Click "Add roles and features" under Configure this local server. 
<img width="2560" height="1440" alt="Screenshot (51)" src="https://github.com/user-attachments/assets/2c366274-7a11-4f43-809f-52509d075f65" />

# Step 29
> Click next on the setup wizard.
<img width="2560" height="1440" alt="Screenshot (52)" src="https://github.com/user-attachments/assets/76c7c4fc-599f-4fce-9c54-fe210a20f5ea" />

# Step 30
> Select "Role-based or feature-based installation", then click next.
<img width="2560" height="1440" alt="Screenshot (53)" src="https://github.com/user-attachments/assets/e171ffc0-3d0a-4f37-81f3-8c33df132535" />

# Step 31
> Leave as default, click next.
<img width="2560" height="1440" alt="Screenshot (54)" src="https://github.com/user-attachments/assets/73dab631-0c73-4d3f-9fd4-d8beea5a808a" />

# Step 32
> Select "Active Directory Domain Services" and "DNS Server" under roles, click next.
<img width="2560" height="1440" alt="Screenshot (56)" src="https://github.com/user-attachments/assets/3fd50464-af0c-4112-b7f8-2e13255ccacc" />

# Step 33
> Leave as default, ensure "Group Policy Management" is selected, then click next.
<img width="2560" height="1440" alt="Screenshot (57)" src="https://github.com/user-attachments/assets/8fc7313e-a9de-41b3-b90d-ae1ca1e74546" />

# Step 34
> Click next.
<img width="2560" height="1440" alt="Screenshot (58)" src="https://github.com/user-attachments/assets/3367263d-5f73-4951-9010-2b071c1e45de" />

# Step 35
> Click next.
<img width="2560" height="1440" alt="Screenshot (59)" src="https://github.com/user-attachments/assets/a45f095b-3e09-4adb-8159-2021ec30a0c4" />

# Step 36
> Click Install.
<img width="2560" height="1440" alt="Screenshot (60)" src="https://github.com/user-attachments/assets/8c640c98-54fc-48f9-9b07-057e57cf3bb4" />

# Step 37
> Wait for install to finish, a new popup will appear.
<img width="2560" height="1440" alt="Screenshot (62)" src="https://github.com/user-attachments/assets/73b80def-9bf4-480c-9bdb-ccfe0558af92" />

# Step 38
> Select "Add a new forest", then name the Root domain name to and ensure it ends in .local , then click next.
<img width="2560" height="1440" alt="Screenshot (65)" src="https://github.com/user-attachments/assets/ac65e218-a9fb-40c3-bf1f-3c2475e38d01" />

# Step 39
> Leave as default, and enter a secure restoration password, then click next.
<img width="2560" height="1440" alt="Screenshot (66)" src="https://github.com/user-attachments/assets/0b5d7325-decb-438e-883f-c78ac3de6ad5" />

# Step 40
> Click next.
<img width="2560" height="1440" alt="Screenshot (68)" src="https://github.com/user-attachments/assets/56bad031-563c-4f58-8214-fd3cd66cf0a9" />

# Step 41
> Leave as the generated default, then click next
<img width="2560" height="1440" alt="Screenshot (69)" src="https://github.com/user-attachments/assets/76cc5edc-4fe7-4293-9f2e-af481fa8be90" />

# Step 42
> Leave as default, then click next.
<img width="2560" height="1440" alt="Screenshot (70)" src="https://github.com/user-attachments/assets/0b230ba5-6f51-4987-996f-004b37e1fd10" />

# Step 43
> Review selections, then proceed by clicking next.
<img width="2560" height="1440" alt="Screenshot (71)" src="https://github.com/user-attachments/assets/b1081635-cde4-4380-8269-2666e9226a74" />

# Step 44
> Verify that the pre-requisite test sucessfully passes and allows installation, then click install. (We will be configuring the network settings shortly afterwords)
<img width="2560" height="1440" alt="Screenshot (72)" src="https://github.com/user-attachments/assets/4fa37acf-f80e-4a52-96b4-d182e174a9a0" />

# Step 45
> After installation, a system restart will initiate and leave you back on the lock screen.
<img width="2560" height="1440" alt="Screenshot (78)" src="https://github.com/user-attachments/assets/34ac86bb-f94d-4a74-9663-4abb9b76031b" />
