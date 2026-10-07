# MediaRunner

> This application is built by AI. I made this for myself and I'm uploading it to GitHub for backup and to share in case anyone can get any use out of it. It's pretty specific to my setup and my needs, but if you can get any use out of it, then enjoy.
>
> Use at your own risk. I offer no warranty or guarantees for this software.

## Getting started

```
MEDIARUNNER
===========

One window to look after the media apps on your home server: Sonarr,
Radarr, NZBGet, Overseerr, Prowlarr, Tautulli and Portainer, plus the
server's own CPU, memory and disks. Look at what is downloading, approve
requests, restart a container, and more, without opening each app's web page.

MediaRunner talks to your apps over your home network. They need to be
running already; it does not install or replace any of them.


GETTING STARTED
---------------
Pick one. Both give you the same app.

OPTION 1 - INSTALLER (recommended)
  Download the file ending in _Setup.exe, double-click it and click Install.
  It installs just for you (no admin password) and adds Start menu and
  Desktop shortcuts. Needs Windows 10 or 11 (64-bit).
  To remove it later: Windows Settings > Apps > MediaRunner > Uninstall.

OPTION 2 - NO INSTALL (zip)
  1. Download the file ending in _no-install.zip. Right-click it -> Extract
  All... and put the MediaRunner folder somewhere it can stay (for example
  Documents). Don't run it from inside the zip.
  2. Double-click MediaRunner.exe. Nothing is installed; to remove it, delete
  the folder.

EITHER WAY
  The first time, MediaRunner opens on the Settings tab. Connect your apps as
  described below.

"Windows protected your PC"? Click "More info" -> "Run anyway".
Windows shows that for apps downloaded from the internet that aren't
signed with a paid certificate.


CONNECTING YOUR APPS
--------------------
1. Open the Settings tab.
2. SERVER ADDRESS: the address of the computer that runs your apps, for
   example 192.168.1.50. One address is used for every app.
3. Click an app's name in the row of buttons, check the PORT (the usual one
   is already filled in), paste its key, and press Test connection.
   A small dot on an app's button means a key is saved for it.

Where to find each key:
- Sonarr, Radarr, Prowlarr: the app's Settings > General > API Key.
- Overseerr: Settings > General > API Key (use the admin's key).
- Tautulli: Settings > Web Interface > API Key.
- NZBGet: no key. Use the ControlUsername and ControlPassword from
  NZBGet's Settings > Security.
- Portainer: click your user name > My account > Access tokens > Add access
  token. Copy it right away; Portainer shows it only once. If Portainer is on
  port 9443, type 9443 as the port; MediaRunner then uses its secure address.
- Server (Glances): no key. See THE SERVER TAB below.


USING IT
--------
Home
- A card for each app with a green or red light, plus the useful numbers:
  what is downloading and coming up, NZBGet's speed (Pause all / Resume
  all), requests waiting, indexers working, who is watching, containers
  running, CPU and memory, and the free space on your disks.
- Click a card to open that app's tab. It refreshes itself every 10 seconds.
- Click a disk on the Disk space card to rename it or hide it. "N hidden -
  show all" brings hidden disks back.
- Arrange cards (top right) lets you drag any card onto another card to move
  it there. Press Done arranging when you're finished. Reset order puts the
  cards back the way they started.

Shows (Sonarr) and Movies (Radarr)
- Search, sort, and switch between a list and a wall of posters.
- Add a show or movie, remove one, search for missing episodes, pick a
  release yourself, or remove a bad file and block that release.

Downloads (NZBGet)
- What is downloading now, with Pause all / Resume all, plus History
  (filter All / Success / Failure / Deleted / Dupe) and Messages
  (filter All / Info / Warning / Error).

Requests (Overseerr)
- What your family asked for. Approve opens a small window to choose the
  quality, folder, language, server, seasons and who it is for. Decline asks
  first. The tab shows how many requests are waiting.

Tautulli
- Who is watching right now, the play history, and stats for the last 30
  days.

Portainer
- All your Docker containers with Running / Stopped counts and their CPU and
  memory use. Click one to Restart, Stop or Start it, or to read its log.


THE SERVER TAB (Glances)
------------------------
The Server tab shows your server's CPU, load, memory, disks, network speed
and temperatures. It reads them from Glances, a small free app that runs as
a container next to your others. To set it up (about 3 minutes):
  1. In Portainer, open Stacks > Add stack and name it glances.
  2. Paste this into the editor, then press Deploy the stack:

       services:
         glances:
           image: nicolargo/glances:latest-full
           container_name: glances
           restart: unless-stopped
           pid: host
           network_mode: host
           environment:
             - GLANCES_OPT=-w
           volumes:
             - /var/run/docker.sock:/var/run/docker.sock:ro
             - /:/rootfs:ro
             - /etc/os-release:/etc/os-release:ro

  3. In MediaRunner, open Settings > Server (Glances) and press Test
     connection. The port is 61208 and there is no key.
The same steps, with a Copy button, are shown on the Server tab until
Glances answers. Click a disk there to rename or hide it.


SETTINGS
--------
- Server address, and a port + key for each app.
- Theme: Runner (neon), Dark, Light, Orchid or Princess.
- Updates: Check for updates, and a tick box to check when MediaRunner starts.


GOOD TO KNOW
------------
- Your keys are saved scrambled (protected by your Windows login), not as
  plain text. If you move MediaRunner to a different PC or Windows user,
  type the keys in again.
- Settings are kept in %APPDATA%\MediaRunner\settings.txt.
- Updates: when MediaRunner starts it checks GitHub for a newer version (it
  only reads the public release page; nothing is sent). If there is one it
  asks whether to update. With the installer, Update now downloads the new
  installer and runs it; with the no-install zip, it opens the download page.
  Settings > Check for updates checks on demand, and the tick box turns the
  startup check off.
- If something goes wrong, MediaRunner-log.txt next to MediaRunner.exe says
  what.
- To remove MediaRunner: delete its folder (or uninstall it), plus
  %APPDATA%\MediaRunner.
```

