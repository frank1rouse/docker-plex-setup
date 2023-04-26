# Docker Plex Setup


## Portainer
I will be using portainer to get a better visual of the entire installation

https://docs.portainer.io/start/install-ce/server/docker/linux

From the instructions above the 2 commands need to be run.

docker volume create portainer_data

docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest

## Firewall Configuration

Check the status of the firewall and enable
'''bash
ufw status
ufw enable
'''
