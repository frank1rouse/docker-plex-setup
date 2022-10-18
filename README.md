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

6. Now we need to ensure that we can connect remotely through ssh.

systemctl ssh.service status

As of this writing the service was installed and started automatically. We therefore need to put credentials into local hosts.

From local box create a public/private key pair with the command below

ssh-keygen

7. Just for my own preference I set the hostname of the box to be plex and rebooted.

sudo vim /etc/hostname

sudo /bin/reboot
Once this is created you need to find the ip address of the new box and ensure that you can ssh into that box.

"ip a" will show you the local address of the box.

run "ssh ubuntu@<local ip address>" to ensure that you can log in with the password created during the install.
  
Once you have that running you can copy your key to the remote box with the command.
  
"ssh-copy-id ubuntu@192.168.86.33"
  
This copies your public key into the remote box authorized_keys file. You should now be able to ssh inot the box without a password.
  
ssh ubuntu@192.168.86.33

To simplify things you can create a config file in the .ssh directory and create a shortcut name for the connection
  
    Host plex
    HostName 192.168.86.33
    User ubuntu
 
When connecting through powershell only the ssh-copy-id utility is not there. You will have to cut and paste the id_rsa.pub key from that box into the known_hosts
  file on the remote box. The same instructions apply for the creation of the config file.
  

8. Now we need to get docker installed on the pi. I am following intructions from the site below 

https://www.simplilearn.com/tutorials/docker-tutorial/raspberry-pi-docker

curl -fsSL https://get.docker.com -o get-docker.sh
sudo usermod -aG docker ubuntu
