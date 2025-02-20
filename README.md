# ALEPH.IM Core Resource Node (CRN) Installation Script
### Overview
This script automates the installation and configuration process of a Core Resource Node (CRN) for the ALEPH.IM network.<br>
It brings all configurations needed in one script.<br>
Follow the guide and make sure you input the correct ips/gateways/domains.


-------------------------------------------------------------------------------------------------------------


### ► The script supports all the aleph-vm versions which are:
  - aleph-vm.debian-12.deb
  - aleph-vm.ubuntu-22.04.deb
  - aleph-vm.ubuntu-24.04.deb
    
**NOTE:** The only tested OS version so far is **Ubuntu 22.04 - both desktop and server versions**.

_____________________________

### ► To run the script:
  1) Make sure you have an internet connection
  2) Open the terminal and paste the following:
 ```bash
 wget https://raw.githubusercontent.com/Pjstolas/CRN.install.sh/refs/heads/main/crn.aleph.install 
 chmod +x crn.aleph.install 
 sudo ./crn.aleph.install 
 ```
    

### ► The script does the following:
  1) Detects if the script is running as sudo or root
  2) Detects OS (for installing the right aleph-vm version)
  3) Asks if the user wants to setup his own networking configuration using **NETPLAN**.<br>
  - If answered yes, the script will install NETPLAN and disable NetworkManager. It will be asked for the IPv4/IPv6 and both gateways. (In some Cloud Providers the users must configure it's own /etc/netplan/50-cloud-init.yaml in order to have a working /64 IPv6)
  - If you want to edit later use `nano /etc/netplan/01-netcfg.yaml`  
  5) Asks for a `subdmain.domain.com` to be configured in `supervisor.env` file and `Caddyfile` as mandatory
  6) Update / upgrade the system
  7) Disables rsyslog.service to prevent excessive disk I/O operations and reduce disk wear
  8) Installs docker and run the vm-connector
  9) installs the appropriate aleph-vm version based on the OS version
  10) Installs Caddy

-------------------------------------------------------------------------------------------------------------

**► After the install user should do a server reboot**
