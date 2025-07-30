## homelab-project
# Overview
#### The goal of this project was to learn how to set up networks, connect services together, create websites and domains, as well as IT fundementals such as firewalls, HTTP/HTTPS, port forwarding, secure external access, and data security. To do this, I began by building a small, power-efficient pc that would allow me to self host a wide variety of services.  
### Current Hardware Setup
#### Main Proxmox Server
* AMD 9600x, 6-Core CPU
* 32 GB DDR5 RAM
* 2x 512 GB nvme drives for container and OS storage
* 2x 12 TB Enterprise harddrives in a mirrored setup for mass storage
<details>
  <summary>First Implementation</summary>
  
  <br>
  <strong>Initial Network Diagram</strong>
  <br>
  <img width="681" height="681" alt="NetworkDiagram" src="https://github.com/user-attachments/assets/8273d398-561f-475e-a3bb-60d3b2c84c21" />
  <br>
  This network diagram can be broken into two major parts, the bare metal Proxmox installation and the LXC container that holds a Portainer instance running many other services. Portainer, or the use of docker in general, cuts down on the number of cores necessary to run the wide range of services I wanted to host on the server, whereas the Proxmox containers were used for more intensive services such as Jellyfin and Immich.
  <br><br>
  <strong> Storage </strong>
  <br>
  The main storage on this server is two 12TB enterprise harddrives that have been set to mirror each other. This increases redundancy, and allows one drive to die while retaining all data stored. Due to the minimal amount of data that will be stored, the loss of capacity is well worth the trade off for redundancy.
  <br><br>
  <strong>Services Hosted</strong><br>
- <strong>Immich:</strong> Self-hosted photo/video storage with face search.<br>
- <strong>Vaultwarden:</strong> Local password manager.<br>
- <strong>Jellyfin:</strong> Media streaming to any device.<br>
- <strong>Jellyseerr, Sonarr, Radarr, Prowlarr, Deluge:</strong> Automated media downloads, routed through GlueTun to a VPN.<br>
- <strong>Tailscale:</strong> Secure remote access.<br>
- <strong>NGINX Proxy Manager:</strong> Custom domain and reverse proxy.<br>
- <strong>Homepage:</strong> Service monitoring and API stats.<br>
</details>

