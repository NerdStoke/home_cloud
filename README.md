# Home Cloud
Instructions and scripts for setting up a home NAS with hard drives and Raspberry Pi

## Introduction


- For instructions in greater detail, we have copied the exact version that we used for this project at [this link](https://github.com/NerdStoke/home_cloud/blob/master/Adden-B-Installing_OMV5_on_an%20R-PI.pdf). However, this documentation may be outdated and the official copy is maintained by [OpenMediaVault](https://github.com/OpenMediaVault-Plugin-Developers/docs/blob/master/Adden-B-Installing_OMV5_on_an%20R-PI.pdf)

## Creating the Raspberry Pi SD Card

1. Download the official [Minimal Image Debian Buster](https://www.raspberrypi.org/downloads/raspberry-pi-os/) version of the Raspberry Pi OS. This is what we will be using as our initial operating system for the Raspberry Pi
2. Download [balenaEtcher](https://www.balena.io/etcher/). This program allows you to flash the Operating System image you just downloaded onto the SD card
3. Etch the OS file onto the SD Card with balenaEtcher

## Configuring the Raspberry Pi

Run the following commands:

`sudo apt update`  

`sudo apt upgrade`  
- The two previous commands will take a while to finish


`https://raw.githubusercontent.com/NerdStoke/home_cloud/master/install.sh | sudo bash`  
- This will also take a while. The Raspberry Pi will automatically reboot when done.
- The previous command is the version that we used, but the script behind it is not maintained. If it ran successfully, then ship the rest of this item. For the official script maintained by OpenMediaVault, run this command: `https://raw.githubusercontent.com/OpenMediaVault-Plugin-Developers/installScript/master/install | sudo bash`

