# Home Cloud
Instructions and scripts for setting up a home NAS with hard drives and Raspberry Pi


## Introduction

- The following instrucitons are written for a windows machine. Every step on the windows machine has an analogous command for linux/mac, so this tutorial can still be completed be replacing a few commands with unix versions. 
- For instructions in greater detail, we have copied the instructions for the exact version that we used for this project at [this link](https://github.com/NerdStoke/home_cloud/blob/master/Adden-B-Installing_OMV5_on_an%20R-PI.pdf). However, this documentation may be outdated and the official copy is maintained by [OpenMediaVault](https://github.com/OpenMediaVault-Plugin-Developers/docs/blob/master/Adden-B-Installing_OMV5_on_an%20R-PI.pdf)


## Creating the Raspberry Pi SD Card

1. Download the official [Minimal Image Debian Buster](https://www.raspberrypi.org/downloads/raspberry-pi-os/) version of the Raspberry Pi OS. This is what we will be using as our initial operating system for the Raspberry Pi
2. Download [balenaEtcher](https://www.balena.io/etcher/). This program allows you to flash the Operating System image you just downloaded onto the SD card
3. Etch the OS file onto the SD Card with balenaEtcher
4. Before the card is ready, we need to manually add an empty file called `ssh`. This can be created with any text editor and shuould be saved in the top level of the card. 


## Connecting to the Raspberry Pi

If you have an HDMI cord, a monitor, and keyboard, you can simply connect those to the Pi and skip this section.  

1. We need to find the IP address of the Raspberry Pi. Before you hook up your Pi, run `arp -a` to see a list of IP addresses on your network. Once the Pi is connected, we will use this command again to see the Pi's new IP, so take note of the IPs that exist now. If you are running linux/mac this command will be different.
2. Insert the SD card into the Raspberry Pi. It may take a few minutes for it to boot.
3. Connect the Raspberry Pi to the internet with an ethernet cord.
4. After a few minutes, run the command `arp -a` again. The new IP is your Pi's IP.



##Configuring the Raspberry Pi

On the Raspberry Pi, run the following commands:

- `sudo apt update`  

- `sudo apt upgrade`  
    - This command will take a while to finish


- `wget -O - https://raw.githubusercontent.com/NerdStoke/home_cloud/master/install.sh | sudo bash`  
    - This will also take a while. The Raspberry Pi should automatically reboot when done. If it does not, then run `sudo reboot`
    - The previous command is the version that we used, but the script behind it is not maintained. If it ran successfully, then skip the rest of this item. For the official script maintained by OpenMediaVault, run this command: `wget -O - https://raw.githubusercontent.com/OpenMediaVault-Plugin-Developers/installScript/master/install | sudo bash`
