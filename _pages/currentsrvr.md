---
title: Current Server Setup
---

# picture of the setup:

![JMCD Image](/docs/assets/jmcdlab.jpeg)

# Items From Left to Right - Top to Bottom

|Object|What it is|
|------|----------|
|Switch|Mikrotik CSS326-24G-2S+RM|
|Router|Sophos SG 230 Rev.1|
|Big Server|Custom Built Server|
|Monitor|Random Acer Monitor|
|UPS|CyberPower CP1500PFCRM2U UPS|

Notes:
- The rack is missing because my car is small and I did not feel like dismantling it and bringing it with me to college for my last semester, I have a 24 port patch panel on it and it is currently sitting at home (picture of it in the old DELLR430 folder)
- More information about the server build can be found in [this post](/2025/02/03/NewServerSetup.html), TLDR: running Truenas Scale, jmcd chassis (chinese and bought off aliexpress and waited over a month) has a AMD EPYC 7402p CPU, 256 of DDR4 ECC Ram, Supermicro H11SSL-i motherboard, 144TB Raw storage(12x 12TB), RTX 3050 (for cuda w/ ai), and a 10gbe nic

### Services being hosted in no particular order, everything is dockerized, the host OS is Truenas Scale:

|Service|Usecase|
|-------|-------|
|[Portainer](https://www.portainer.io/)| Docker Management|
|[WUD (What's up Docker)](https://github.com/getwud/wud)|Container update watching|
|[Homepage](https://github.com/benphelps/homepage)|Hosted Services Dashboard|
|[CyberChef](https://github.com/gchq/CyberChef)|Cyber Swiss Army Knife|
|[Open WebUI + Ollama](https://github.com/open-webui/open-webui)|Local LLMs + WebUI|
|[Glances](https://github.com/nicolargo/glances)|System Resources Monitoring|
|[TubeArchivist](https://github.com/tubearchivist/tubearchivist)|Youtube Downloader and Archiver|
|[Gluetun](https://github.com/qdm12/gluetun)|VPN for docker containers, needed for TubeArchivist to prevent IP rate limits|
|[Vikunja](https://github.com/go-vikunja/vikunja)|Todo Task Tracking|
|[Baikal](https://github.com/sabre-io/Baikal)|CalDAV + CardDAV server|
|[The Lounge](https://github.com/thelounge/thelounge)|IRC Client|
|[Planka]((https://github.com/plankanban/planka))|Kanban Board for Task Tracking|
|[Speedtest Tracker](https://github.com/alexjustesen/speedtest-tracker)|Hourly Internet Speed Tests|
|[qBittorrent](https://github.com/qbittorrent/qBittorrent/) + [VueTorrent WebUI](https://github.com/VueTorrent/VueTorrent)|Torrent Client, mostly used with the [Internet Archive](https://archive.org/)|
|[Joplin Sync Server](https://github.com/laurent22/joplin)|Notes Syncing|
|[Nginx Proxy Manager](https://github.com/NginxProxyManager/nginx-proxy-manager)|Reverse Proxy|
|[Mumble](https://github.com/mumble-voip/mumble-docker)|Voip Server|
|[Screego](https://github.com/screego/server)|Screen Sharing|
|[Filebrowser](https://github.com/filebrowser/filebrowser)|WebUI for File Browsing|
|[FreshRSS](https://github.com/FreshRSS/FreshRSS)|RSS Feed Reader|
|[Navidrome](https://github.com/navidrome/navidrome)|Local Music Server |

### On the OPNsense router (not docker):

- The router runs [OPNsense](https://opnsense.org/)
- [Adguard Home](https://github.com/AdguardTeam/AdguardHome) for DNS ad blocking

### Other things on the server not dockerized:

- Multiple Debian VMs for testing various software and running scripts not meant to run on the base truenas scale OS
