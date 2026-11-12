# MediaRunner

One window to look after the media apps on your home server: Sonarr, Radarr, NZBGet, Overseerr, Prowlarr, Tautulli and Portainer, plus the server's own CPU, memory, disks and RAID, drive health (Scrutiny) and Maintainerr. Look at what is downloading, approve requests, restart a container, and more, without opening each app's web page.

MediaRunner talks to your apps over your home network (or any address you give it). They need to be running already; it does not install or replace any of them.

### Features

- A Home page with a card for each app: a green or red light, what is downloading, what is coming up, requests waiting, who is watching, running containers, and the server's CPU, memory and disks
- Shows (Sonarr) and Movies (Radarr): browse, add, remove, search, pick a release yourself, and fix bad downloads. Open a movie or show for its ratings and cast with photos, and click an actor to see what else of theirs you have
- Tick several shows or movies at once to remove them
- Downloads (NZBGet), Requests (Overseerr), Tautulli and Portainer tabs
- A Server tab with CPU, load, memory, disks, network and temperatures
- Home cards for RAID health, drive health (Scrutiny) and Maintainerr
- Profiles, so one window can switch between Home, Away or another server
- 19 themes (Runner, Dark, Light, Orchid, Princess, HCN Radio and the ship makers), and it checks for new versions when it starts

> This application is built by AI. I made this for myself and I'm uploading it to GitHub for backup and to share in case anyone can get any use out of it. It's pretty specific to my setup and my needs, but if you can get any use out of it, then enjoy.
>
> Use at your own risk. I offer no warranty or guarantees for this software.

## Download

**Latest version: v1.5** (Nov 12, 2026)

- [MediaRunner_v1.5_no-install.zip](https://github.com/codenomics/MediaRunner/releases/download/v1.5/MediaRunner_v1.5_no-install.zip) - 174 KB
- [MediaRunner_v1.5_Setup.exe](https://github.com/codenomics/MediaRunner/releases/download/v1.5/MediaRunner_v1.5_Setup.exe) - 212 KB
- [MediaRunner_v1.5_source.zip](https://github.com/codenomics/MediaRunner/releases/download/v1.5/MediaRunner_v1.5_source.zip) - 155 KB

What's new in v1.5:

- Home: three new cards, RAID health (read from your server's Linux RAID through a small helper container), drive health from Scrutiny, and Maintainerr
- Shows: open a show to see its rating, an Open on IMDb link and the cast with photos
- Movies and Shows: click an actor to see every movie and show of theirs that is in your library, and open it from there
- Settings: Scrutiny and Maintainerr can be connected (no key needed); the app buttons now wrap onto a second row
- Themes: 14 new looks pick-able in Settings, HCN Radio plus the ship makers (Aegis, Aopoa, Argo, Banu Souli, Crusader, Drake, Esperia, Gatac, Grey's Market, Kruger, MISC, Origin and RSI)
- Home: Arrange cards now lets you resize a card between half and full width, and drop a card exactly where the pink line shows (even a full-width card above two half-width ones)

Older versions are on the [Releases page](https://github.com/codenomics/MediaRunner/releases).

## Getting started

### Installer (recommended)

1. Download the file ending in `_Setup.exe` above.
2. Double-click it and click Install. It installs just for you - no admin password needed - and adds Start menu and Desktop shortcuts.
3. To remove it later: Windows Settings > Apps, find MediaRunner and click Uninstall.

### No install (portable zip)

1. Download the file ending in `_no-install.zip` above.
2. Right-click it > Extract All, and pick a folder. Don't run it from inside the zip.
3. Open the folder and double-click the app's .exe. Nothing is installed; delete the folder to remove it.

Windows says "Windows protected your PC"? Click More info > Run anyway. It shows that for apps without a paid signing certificate.

## Source code

Want to see how it works, or build it yourself? Download the file ending in `_source.zip` above, extract it and double-click `Build.bat`. It only uses the C# compiler that already comes with Windows, so there is nothing to install.

## More details

```
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
- Server (Glances), RAID, Scrutiny and Maintainerr: no key. Just check the port
  (61208, 61209, 8080 and 6246). See THE SERVER TAB and THE RAID CARD below.


USING IT
--------
Home
- A card for each app with a green or red light, plus the useful numbers:
  what is downloading (Sonarr and Radarr count what NZBGet is downloading
  for them) and coming up, NZBGet's speed (Pause all / Resume
  all), requests waiting, indexers working, who is watching, containers
  running, CPU and memory, and the free space on your disks.
- Three more cards: RAID health (for Linux software RAID, mdadm), drive
  health from Scrutiny, and Maintainerr's collections and what is due to be
  removed.
- Click a card to open that app's tab. It refreshes itself every 10 seconds.
- Click a disk on the Disk space card to rename it or hide it. "N hidden -
  show all" brings hidden disks back.
- Arrange cards (top right) lets you move and resize the cards. Drag a card
  and a pink line shows where it will land (a full-width card can go above a
  pair of half-width ones); the button on each card switches it between half
  and full width. Press Done arranging when you're finished. Reset order puts
  the cards back the way they started.

Shows (Sonarr) and Movies (Radarr)
- Search, sort, and switch between a list and a wall of posters.
- Add a show or movie (it remembers the folder and quality you picked last),
  remove one, search for missing episodes, pick a release yourself, or
  remove a bad file and block that release.
- Select: tick several shows or movies (in the list or the poster view) and
  remove them in one go.
- Open a movie or show to see its ratings, age rating, genres, director or
  creator, and an Open on IMDb link, plus the cast with photos (the photos come
  from Overseerr, so connect it in Settings).
- Click an actor to see their page and every movie and show of theirs in your
  library. Click one to open it.

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


THE RAID CARD
-------------
The RAID card on the Home page shows whether your Linux software (mdadm)
RAID is healthy, how many drives are working and how many are spares, and a
check or rebuild while one is running. It reads the server's /proc/mdstat
through a tiny helper container. To set it up (about 2 minutes):
  1. In Portainer, open Stacks > Add stack and name it mdstat.
  2. Paste this into the editor, then press Deploy the stack:

       services:
         mdstat:
           image: alpine/socat
           container_name: mdstat
           restart: unless-stopped
           network_mode: host
           entrypoint: /bin/sh
           command:
             - -c
             - |
               printf '%s\n' '#!/bin/sh' 'while read l && [ "$${#l}" -gt 1 ]; do true; done' 'printf "HTTP/1.0 200 OK\r\n\r\n"' 'cat /proc/mdstat' > /tmp/h.sh
               chmod +x /tmp/h.sh
               exec socat TCP-LISTEN:61209,fork,reuseaddr EXEC:/tmp/h.sh

  3. In MediaRunner, open Settings > RAID and press Test connection. The
     port is 61209 and there is no key.
It only shows RAID that Linux itself manages (mdadm). A RAID controller card
or a ZFS pool won't show up.


PROFILES (HOME, AWAY ...)
-------------------------
Settings > Profile (top right) keeps a separate server address, ports and keys
for each place you connect from, or for a second server.
- New makes a copy of the profile you are using. Change the server address (and
  anything else that is different), then press Test connection.
- Pick a profile in the list to switch to it. The whole app switches, and the
  window title shows the profile name once you have more than one.
- Rename and Delete work on the profile shown in the list.
MediaRunner only talks to the address you type. To reach your server from
outside your home you still need a way in, such as a VPN back to your network.


SETTINGS
--------
- Profile, server address, and a port + key for each app.
- Theme: Runner (neon), Dark, Light, Orchid, Princess, HCN Radio, or a ship maker look (Aegis, Aopoa, Argo, Banu Souli, Crusader, Drake, Esperia, Gatac, Grey's Market, Kruger, MISC, Origin and RSI).
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

