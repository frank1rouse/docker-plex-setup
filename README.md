# docker-plex-setup

Laptop close lid behavior
https://fostips.com/lid-close-action-ubuntu-21-04-laptop/

Add user to docker group
https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04

Start portainer
https://docs.portainer.io/v/2.14/start/install/server/docker/wsl

Firewall for both ssh and portainer
https://linuxconfig.org/firewall-ufw-status-
inactive-on-ubuntu-20-04-focal-fossa-linux

https://www.cyberciti.biz/faq/how-to-open-firewall-port-on-ubuntu-linux-12-04-14-04-lts/

Add the mountpoints for the external drives
https://kenfavors.com/code/mounting-an-external-drive-on-ubuntu-server/
https://askubuntu.com/questions/113733/how-to-mount-a-ntfs-partition-in-etc-fstab

To find the uuid associated with the drive issue the command below as root
ls -l /dev/disk/by-uuid/

root@frouse-Inspiron-7570:/home/frouse# ls -l /dev/disk/by-uuid/
total 0
 lrwxrwxrwx 1 root root 10 Nov 28 23:56 54D8D96AD8D94ABE -> ../../sdd1
 lrwxrwxrwx 1 root root 10 Nov 28 23:53 6217-6C8B -> ../../sdc2
 lrwxrwxrwx 1 root root 10 Nov 28 23:53 67E3-17ED -> ../../sdc1
 lrwxrwxrwx 1 root root 10 Nov 27 18:22 8E16D96416D94E39 -> ../../sdb1
 lrwxrwxrwx 1 root root 10 Nov 27 14:55 A387-C69A -> ../../sda1
 lrwxrwxrwx 1 root root 10 Nov 27 14:55 b01a5310-9586-4ef9-87a6-982f488155cb -> ../../sda2

or

blkid
 /dev/sdd1: LABEL="My Book" BLOCK_SIZE="4096" UUID="54D8D96AD8D94ABE" TYPE="ntfs"
 /dev/sdb1: LABEL="My Passport" BLOCK_SIZE="512" UUID="8E16D96416D94E39" TYPE="ntfs" PARTLABEL="My Passport"  PARTUUID="c0370cd4-b8da-4773-8c8f-f413d4ab7da2"
 /dev/sdc2: LABEL="LaCie" UUID="6217-6C8B" BLOCK_SIZE="512" TYPE="exfat" PARTUUID="e6cc195a-95df-11ec-ac82-6045cba1c494"
 /dev/sdc1: LABEL_FATBOOT="EFI" LABEL="EFI" UUID="67E3-17ED" BLOCK_SIZE="512" TYPE="vfat" PARTLABEL="EFI System Partition"  PARTUUID="e6cc1959-95df-11ec-ac82-6045cba1c494"

It seems the LaCie has two partitions





