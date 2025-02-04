---
title: Old Dell R430 Setup
date: 2025-02-03
---
# Picture of the setup:
![Dell R430 image](/docs/assets/DELLR430LAB.png)

# Items From Top to Bottom

|Object|What it is|
|---|---|
|Monitor|Random Acer Monitor|
|Router|Sophos SG 230 Rev.1|
|Switch|SODOLA 16 Port Gigabit Ethernet Network Switch|
|Patch Panel|C2G Legrand 16 Port Patch Panel|
|Server|Dell PowerEdge R430 4B LFF|
|Chromebox|Asus Chromebox flashed with coreboot to run debian|
|Shelf|startech.com 1u server rack shelf|
|Outlets|startech.com 16 outlet|
|UPS|CyberPower CP1500PFCRM2U UPS|
|Rack|StarTech.com 12U Rack|

# Major Differences between this and the newer JCMD Build
- I got rid of the chromebox as the newer machine that I built can do VMs a lot better than the r430, so I condensed everything that was on the chromebox onto a VM on the new server
- The main OS I was using, [openmediavault](https://github.com/openmediavault/openmediavault), was changed for [truenas scale](https://www.truenas.com/truenas-scale/) as I have a lot more drives and wanted a ZFS centric setup since the long term integrity of data is one of my #1 priorities
- The switch I had was changed to a Mikrotik switch with more ports, I wanted a managed switch to mess with, and I also wanted fiber connectivity
	- this was also coupled with getting a new patch panel so I could have all of the ports on the switch populated
- The router now has a checkpoint fiber module to connect to the switch and then to a gigabic nic on the new server
- The startech outlet is gone and everything plugs directly into the UPS instead
- The services I was using for docker update notifications, that being [diun](https://github.com/crazy-max/diun) with a [gotify server](https://github.com/gotify/server) was condensed into one application, that being [WUD](https://github.com/getwud/wud)
- [pi-hole](https://github.com/pi-hole) was swapped for [adguard home](https://github.com/AdguardTeam/AdguardHome) as this allows me to run adguard home, therefore the dns server, on my router instead of my server
- similarly, [wireguard easy](https://github.com/wg-easy/wg-easy) was removed from my setup as I was able to setup wireguard on my router, so if I need to remotely manage the server itself and restart docker (or the server) I don't lose VPN connectivity
