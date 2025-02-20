This is a simple script to automate a few steps in the process of installing a Core Resource Node (**CRN**) for the ALEPH.IM project.

The script supports all the aleph.im OS versions. 
**NOTE**: The only tested OS version so far is **Ubuntu 22.04**.


**To run the script:**
  1) Make sure you have an internet connection
  2) Open the terminal: 
  3) "wget https://raw.githubusercontent.com/Pjstolas/CRN.install.sh/refs/heads/main/crn.aleph.install"     # Download the script to your server
  4) "chmod +x crn.aleph.install"    # Makes the script executable by your user
  5) "sudo ./crn.aleph.install"      # runs the script with sudo to install everything and make the necessary configurations
    

**The script does the following:**
  1) Detects if the script is running as sudo or root
  2) Detects OS (for installing the right aleph version)
  3) Asks if the user wants to setup his own networking configuration using **NETPLAN**. If answered yes, it starts the installation and it will be asked the IPv4/IPv6 addresses and respective gateways. (In some Cloud Providers users must configure it's own netplan/50-cloud-init.yaml file in order to have a working /64 IPv6)
  4) Asks for a **subdmain.domain.com** to be configured in supervisor.env file and Caddyfile as mandatory
  5) Update / upgrade the system
  6) Disables rsyslog.service to prevent excessive disk I/O operations and reduce disk wear
  7) Installs docker and run the vm-connector
  8) installs the appropriate aleph-vm version based on the OS version
  9) Installs Caddy
  10) 
  
