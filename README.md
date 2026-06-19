# My Windows Active Directory 2022 Homelab
<br>

## What is this?
>This is a collection of documentation from my recent Active Directory Homelab involving Windows Server 2022
## Whats the point?
>The point of this lab is to gain hands on experience in working with Active Directory in a business environment. I believe true understanding is only ever achived when you are able to explain the subject to another person with no experience, so this lab will follow more of a 'How to' style format.
## What was used?
> This lab was completed using a Desktop PC running a 14th Gen Intel i5 Processor, 16gb of DDR5 RAM, and a NVIDIA RTX 4060 8gb. The software used was VMware Workstation Pro 25H2 provided by Broadcom, the Operating Systems include Windows Server 2022 Standard, and Windows 11 Pro.
> 16GB of Memory is recommended at minimum as we will be allocating 10GB of Memory just in Virtualization to meet minimum requirements.
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
>Name the Virtual Machine to something memorible such as Win11_Client_1, then click next.
><img width="2559" height="1439" alt="Screenshot 2026-06-17 194258" src="https://github.com/user-attachments/assets/c2c8f1c0-3519-4c2b-8d6e-bf178cea1553" />

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
