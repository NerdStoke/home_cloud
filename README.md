# Home Cloud
Instructions and scripts for setting up a home NAS with hard drives and Raspberry Pi


## Introduction

- The following instrucitons are written for a windows machine. Every step on the windows machine has an analogous command for linux/mac, so this tutorial can still be completed be replacing a few commands with unix versions. 
- For instructions in greater detail, we have copied the instructions for the exact version that we used for this project at [this link](https://github.com/NerdStoke/home_cloud/blob/master/Adden-B-Installing_OMV5_on_an%20R-PI.pdf). However, this documentation may be outdated and the official copy is maintained by [OpenMediaVault](https://github.com/OpenMediaVault-Plugin-Developers/docs/blob/master/Adden-B-Installing_OMV5_on_an%20R-PI.pdf).


## Creating the Raspberry Pi SD Card

1. Download the official [Minimal Image Debian Buster](https://www.raspberrypi.org/downloads/raspberry-pi-os/) version of the Raspberry Pi OS. This is what we will be using as our initial operating system for the Raspberry Pi.
2. Download [balenaEtcher](https://www.balena.io/etcher/). This program allows you to flash the Operating System image you just downloaded onto the SD card.
3. Etch the OS file onto the SD Card with balenaEtcher.
4. Before the card is ready, we need to manually add an empty file called `ssh`. This can be created with any text editor and shuould be saved in the top level of the card. 


## Connecting to the Raspberry Pi

1. With an HDMI cord and a monitor, connect those to the Pi. The IP address should be displayed within the boot sequence output.  
2. Use that IP to connect to the Pi via SSH with a program like [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) for windows or within the terminal for unix systems.
3. Now we can log in to the Pi On the Raspberry Pi.
    - The default login is the user `pi` with password `raspberry`.
    - Once logged in, this can be changed with the command `sudo passwd`.



## Configuring the Raspberry Pi

Run the following commands:

- `sudo apt update`  

- `sudo apt upgrade`  
    - This command will take a while to finish.

- Now, we need to reboot with `sudo reboot`.


- `wget -O - https://raw.githubusercontent.com/NerdStoke/home_cloud/master/install.sh | sudo bash`  
    - This will also take a while. The Raspberry Pi should automatically reboot when done. If it does not, then run `sudo reboot`
    - The previous command is the version that we used, but the script behind it is not maintained. If it ran successfully, then skip the rest of this item. For the official script maintained by OpenMediaVault, run this command: `wget -O - https://raw.githubusercontent.com/OpenMediaVault-Plugin-Developers/installScript/master/install | sudo bash`.


## Configuring Open Media Vault

Once the Pi has rebooted, you should new be able to visit the IP address of the Pi in a browser by going to `http://[RASPBERRYPIIPADDRESS]`.

The default username is `admin` and default password is `openmediavault`.

You can change the password under **General Settings**.