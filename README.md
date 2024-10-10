# Install-and-Configure-ClamAV

Project: 
Installing ClamAV on Ubuntu Server for PCI-DSS Compliance
In this project, I will demonstrate how to install and configure ClamAV antivirus on 
an Ubuntu server to help meet the PCI-DSS framework requirements. The installation process 
will be documented step-by-step, accompanied by screenshots to provide clear guidance.

Objectives:

Ensure the server is secure by implementing antivirus measures.

Comply with PCI-DSS standards for protecting cardholder data.


I did the project on [Azure](https://azure.microsoft.com/en-us). You can use any platform as you prefer,
All steps are the same. 

If you need help on how to create a VM on Azure, please click [here](https://learn.microsoft.com/en-us/azure/virtual-machines/linux/quick-create-portal?tabs=ubuntu)

Here are the following steps: 

   1. Once log into the VM, the first thing always to make sure the system is up to date.
      
      Run the Following Command: sudo apt update && sudo apt upgrade -y
<p align="center">
<img src="https://imgur.com/ykogwVj.png" height="80%" width="80%" >


  2. After updating, run the following command to install ClamAV:

      sudo apt-get install clamav clamav-daemon
<p align="center">
<img src="https://imgur.com/gTy6uns.png" height="80%" width="80%" >

  3. Checking the Clamav installation:

      dpkg -l | grep -i clamav
<p align="center">
<img src="https://imgur.com/szoB4Bo.png" height="80%" width="80%" >

  4. Check the status of clamav by issuing: systemctl status clamav-freshclam
      
      systemctl status clamav-freshclam
<p align="center">
<img src="https://imgur.com/ND75pCq.png" height="80%" width="80%" >
   
  5. We need to update the ClamAv Signature Database, but we need to stop the service first
      
      sudo systemctl stop clamav-freshclam
<p align="center">
<img src="https://imgur.com/xtpCxKt.png" height="80%" width="80%" >
