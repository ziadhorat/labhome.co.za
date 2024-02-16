# Homelab example
## _"labhome.co.za"_

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Contents

- [Contents](#contents)
- [Screenshots](#screenshots)
- - [Homepage](#screenshots)
- - [Homelab Diagram](#screenshots)
- [Services](#services)
- [Usage](#usage)
- [Footnotes](#footnotes)

## Screenshots

### Homepage

![Homepage](assets/homepage.png?raw=true "Title")


### Homelab Diagram

![Homelab Diagram](assets/diagram.png?raw=true "Title")

## Services:

- **Development**
- - [Portainer](https://hub.docker.com/r/portainer/portainer-ce) - Management of Docker environment.
- - [Prometheus](https://hub.docker.com/r/prom/prometheus) - Prometheus is a systems and service monitoring system. 
- - [Loki](https://hub.docker.com/r/grafana/loki) - Cloud Native Log Aggregation by Grafana.
- - [Portainer](https://hub.docker.com/r/portainer/portainer-ce) - Lightweight service delivery platform for containerized applications.
- - [Grafana](https://hub.docker.com/r/grafana/grafana) - Grafana is the open source analytics & monitoring solution for every database.
- - [Code-Server](https://docs.linuxserver.io/images/docker-code-server/) - Code-server is VS Code running on a remote server, accessible through the browser.  
- - [Gitea](https://docs.gitea.com/installation/install-with-docker) - AForge software package for hosting software development version control using Git.
- - [Gitea-Runner](https://docs.gitea.com/usage/actions/act-runner) - Runner of Gitea Actions.

- **NAS**
- - [Crafty](https://hub.docker.com/r/arcadiatechnology/crafty-4) - Crafty 4 is the next iteration of our Minecraft Server Wrapper/Controller/Launcher.
- - [Plex](https://hub.docker.com/r/linuxserver/plex) - Hosts & organizes movies.
- - [Jellyfin](https://hub.docker.com/r/jellyfin/jellyfin) - The Free Software Media Browser.
- - [Scrutiny](https://github.com/AnalogJ/scrutiny#docker) - WebUI for smartd S.M.A.R.T monitoring.
- - [Samba](https://hub.docker.com/r/adevur/easy-samba) - SAMBA server based on CentOS 8, easy to set up. 
- - [Overseerr](https://hub.docker.com/r/linuxserver/overseerr) - Management and media discovery tool built to work with the Plex ecosystem.
- - [Radarr](https://hub.docker.com/r/linuxserver/radarr) - Movie collection manager for Usenet and BitTorrent users.
- - [Sonarr](https://hub.docker.com/r/linuxserver/sonarr) - PVR for Usenet and BitTorrent users.
- - [Lidarr](https://hub.docker.com/r/linuxserver/lidarr) - Music collection manager for Usenet and BitTorrent users.
- - [Prowlarr](https://hub.docker.com/r/linuxserver/prowlarr) - Indexer manager/proxy built on the popular arr stack to integrate with your various PVR apps.
- - [qBitTorrent](https://hub.docker.com/r/linuxserver/transmission) -  Torrent client. [Common issue](https://github.com/qbittorrent/qBittorrent/issues/8095#issuecomment-472740702)

- **Services**
- - [Homepage](https://gethomepage.dev/) - A modern, fully static, fast, secure fully proxied, highly customizable application dashboard.
- - [Home-Assistant](https://hub.docker.com/r/homeassistant/home-assistant) - Open source home automation that puts local control and privacy first.
- - [qFlood](https://hub.docker.com/r/hotio/qflood) - Torrent client Web UI.
- - [Joplin-Server](https://hub.docker.com/r/joplin/server) - Joplin is an excellent open source note taking application with plenty of features.
- - [File-Gator](https://hub.docker.com/r/filegator/filegator) - FileGator is a free, open-source, self-hosted web application for managing files and folders.
- - [IT-Tools](https://hub.docker.com/r/corentinth/it-tools) - Collection of handy tools for developers.
- - [PairDrop](https://hub.docker.com/r/linuxserver/pairdrop) - Send documents via peer to peer connection over LAN.
- - [Tautulli](https://hub.docker.com/r/tautulli/tautulli) - A Python based monitoring and tracking tool for Plex Media Server.
- - [DrawIO](https://hub.docker.com/r/jgraph/drawio) - Diagram software for making flowcharts, process diagrams, org charts, UML, ER and network diagrams.
- - [Ghost](https://hub.docker.com/_/ghost) - Ghost is a free and open source blogging platform written in JavaScript.
- - [Wordpress](https://hub.docker.com/_/wordpress) - The WordPress rich content management system can utilize plugins, widgets, and themes.

- **Network**
- - [PiHole](https://hub.docker.com/r/pihole/pihole) - DNS sinkhole.
- - [Nginx](https://hub.docker.com/r/jc21/nginx-proxy-manager) - Manage Nginx proxy hosts with a simple, powerful interface. [Config](https://pimylifeup.com/raspberry-pi-nginx-proxy-manager/)
- - [Tailscale](https://hub.docker.com/r/tailscale/tailscale) - Connect your devices and users together in your own secure virtual private network. 
- - [CloudFlared](https://github.com/cloudflare/cloudflared) - Tunneling daemon that proxies traffic from the Cloudflare network to your origins.

- **Databases**
- - [Postgres](https://hub.docker.com/_/postgres) - The PostgreSQL object-relational database system provides reliability and data integrity.
- - [MySQL](https://hub.docker.com/_/mysql) - MySQL is a widely used, open-source relational database management system (RDBMS).

- **Agents on all servers**
- - [WatchTower](https://hub.docker.com/r/containrrr/watchtower) - Automating Docker container base image updates.
- - [Promtail](https://hub.docker.com/r/grafana/promtail) - Agent which ships the contents of local logs to a private Loki instance.
- - [cAdvisor](https://hub.docker.com/r/google/cadvisor) - Provides an understanding of the resource usage and performance characteristics of containers.
- - [Portainer-Agent](https://hub.docker.com/r/portainer/agent) - An agent used to manage all the resources in a Swarm cluster. 

## Usage

- Set up vars file for general & nas.
- Ensure all ports are correctly assigned withink boilerplates.
- !! Change the user and group in all boilerplates from root, root will guarentee it will all work but you should instead use the user generated by the ansible scripts or one on your system already (without root privs).
- Run: `ansible-playbook main.yml`
- After the initial run, gitea + gitea_runners do all future deploys

## Issues

### OrangePi 5 Plus Joshua Riek / Debian eMMc issue

- **If you are using an OrangePi-5Plus, these 2 images work great for a headless OS.** (I use Debian)
- - [Ubuntu (Joshua-Riek)](https://github.com/Joshua-Riek/ubuntu-rockchip/releases)
- - [Debian (OfficalOrangePiTeam)](http://www.orangepi.org/html/hardWare/computerAndMicrocontrollers/service-and-support/Orange-Pi-5-plus.html)
- **I use RKDevTool to flash my eMMc chip with an OS.**
- **If RKDevTool gives you issues:** 
- - Flash a SD card with Ubuntu Dekstop (as that takes boot priority).
- - Boot into the SD card 
- - Run the following **on** the server

```shell
if [ "$wipedisk" == "yes" ]; then
    dd if=/dev/zero of=/dev/mmcblk0 
fi
if [ ${imagename: -3} == "img" ]; then
    tar cJvf ${imagename}.xz ${imagename}
    xz -dc ${imagename}.xz | sudo dd of=/dev/mmcblk0 bs=4k
    sync
fi
if [ ${imagename: -2} == "xz" ]; then
    xz -dc ${imagename} | sudo dd of=/dev/mmcblk0 bs=4k
    sync
fi
```

## Footnotes

>
> **[LinuxServer.IO](https://www.linuxserver.io/)** is a great resource - especially for finding arm64 compatible docker images
>
> Locate services for you: **[Awesome-Selfhosted](https://awesome-selfhosted.net/) / [Awesome-Docker](https://github.com/veggiemonk/awesome-docker)**
>
> Homepage examples: **[u/deleted](https://www.reddit.com/media?url=https%3A%2F%2Fi.redd.it%2F40-containers-counting-v0-zb6gsaxnbzga1.png%3Fs%3D0feb92cca69bb70fb4cf74de6cff0aee8b4e1843)**
>
> This projects backbones was originally forked from **[rishavnandi/ansible_homelab](https://github.com/rishavnandi/ansible_homelab)**
