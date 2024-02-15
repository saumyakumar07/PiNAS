Step 1: Install Raspberry Pi OS Download the Raspberry Pi imager from https://www.raspberrypi.com/software/ and select the image to be installed on the Pi.

For the 4Gb pi I have, I have used the 32 bit Raspberry Pi OS lite from https://downloads.raspberrypi.org/raspios_lite_armhf/images/raspios_lite_armhf-2023-02-22/2023-02-21-raspios-bullseye-armhf-lite.img.xz

Once done, just insert the card into the Pi and use an ssh connection from a different computer to login into the Pi: username “pi”, password “raspberry”.

Then a quick update of the system with:

sudo apt update sudo apt upgrade

Step 2 Install Open Media Vault

The quickest way to install Open Media Vault is to run the script from the developers GitHub page https://github.com/OpenMediaVault-Plugin-Developers/installScript.

sudo wget -O - https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/install | sudo bash

Once installed, open a web browser page and go the IP address of the Pi (router setting might be helpful to find it).

Default username is “admin” and the default password is “openmediavault”.

The interface is quite straightforward to use. Some initial tweaks might be in order like changing the default password, mounting the disks in the Storage option, creating a file system and enabling SMB and/or NFS.

Some user credentials setup will be useful for accessing the drives.

If there are existing folders on the HDD, just create a share with the same name as the existing folder.

Step 3 Install plex on the NAS

Install the GNU/Linux transport software that allows the use of repositories accessed via the HTTP Secure protocol (HTTPS), also referred to as HTTP over TLS.

sudo apt install apt-transport-https Add and check plex repositories:

curl https://downloads.plex.tv/plex-keys/PlexSign.key | sudo apt-key add - echo deb https://downloads.plex.tv/repo/deb public main | sudo tee /etc/apt/sources.list.d/plexmediaserver.list Update repositories and install the plex media server:

sudo apt update sudo apt install plexmediaserver To access the web interface for plex, open a web browser and input the Pi address with the default port for the plex server. For example:

192.168.1.21:32400/web Sign up or sign in to plex and add the raspberry pi NAS to the sources. Raspberry Pi is a great little computer that is more than capable of providing entertainment for home and backing up those beautiful memories on a very functional NAS.

References:

Download Raspberry imager https://www.raspberrypi.com/software/ Raspberry OS 64 bit https://downloads.raspberrypi.org/raspios_lite_arm64/images/raspios_lite_arm64-2021-11-08/ Install script https://github.com/OpenMediaVault-Plugin-Developers/installScript on github Running a 64 bit OS https://pimylifeup.com/raspberry-pi-64-bit/ NetworkChuck https://www.youtube.com/watch?v=gyMpI8csWis GaryExplains https://www.youtube.com/watch?v=O-FfOWdZAQ4 ExplainingComputers https://www.youtube.com/watch?v=bpvlEbdA6qI
