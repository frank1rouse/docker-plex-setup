# docker-plex-setup


All inclusive steps including links to get this up and running

1. Grab raspberry pi software installer and a 32 Gb mico sd card

https://www.raspberrypi.com/software/

2. Once downloaded and installed launch the pi software installer and select the ubuntu server option.

3. Now that the os has been installed insert into the pi-400 and boot.

This is a command line only installation. Once launched log in the the credentials 
Username
ubuntu
Password
ubuntu

4. Once logged in you will be forced to change the password of the ubuntu user. Make is something good as this machine will have ports open on the internet.

5. Update the ubuntu machine to ensure you are using the latest security updates. The second command may take a while and may require a reboot.
sudo apt-get update
sudo apt-get upgrade
