---
title: Hibaelhárítás
description: Everything to solve your problem
published: true
date: 2021-02-08T21:30:58.603Z
tags:
editor: markdown
dateCreated: 2020-06-11T18:03:54.865Z
---

> Make sure you have the extension **and** the application installed! 
> 
> {.is-warning}

Included on this page:
1. [General troubleshooting](https://docs.premid.app/troubleshooting#general)
2. [Linux hibaelhárítás](https://docs.premid.app/troubleshooting#linux)
3. [MacOS hibaelhárítás](https://docs.premid.app/troubleshooting#macos)

<a name="general"></a>

# General troubleshooting
> You can use [this](https://qkeleq10.github.io/PreMiD-Troubleshooting/) tool to more easily identify your issue. 
> 
> {.is-info}
### Frissítsd az oldalt
You can press <kbd>CTRL+R</kbd>/<kbd>F5</kbd> (Windows) or <kbd>CMD+R</kbd> (MacOS) on your keyboard too instead of searching for the refresh button.

### Are you using the Discord app?
PreMiD does **not** work on the browser version of Discord, you must download the app [here](https://discord.com/download).

### Győződj meg arról, hogy engedélyezve vannak a Discord Játék tevékenységek a beállításokban
**Felhasználói beállítások** > **Játék tevékenység** ![activitystatus.png](/activitystatus.png)

### Győződj meg arról, hogy a Discord nem rendszergazdai jogokkal fut
Nagyon fontos. A Discord RCP nem fog futni, ha a Discord rendszergazda jogokkal fut.

### Are you using a presence with settings?
Many presences (including `Twitch` and `SoundCloud`) are affected by an extension issue. This issue causes the extension to not grab the default values of settings properly.

To solve this, all you have to do is toggle the topmost setting: ![presencesettings.gif](/presencesettings.gif)

### Indítsd újra a böngészőt
<kbd>Alt</kbd>+<kbd>F4</kbd> (Windows) vagy a <kbd>CMD</kbd>+<kbd>Q</kbd> (MacOS) hasznos lehet ebben az esetben is. (Nyilvánvalóan, megint el kell indítanod a böngészőt.)

### Indítsd újra a PreMiD alkalmazást
![quit.png](/quit.png) You have to restart PreMiD afterwards.

### Indítsd újra a Discord alkalmazást
Press <kbd>CTRL+R</kbd> (Windows) or <kbd>CMD+R</kbd> (MacOS) on your keyboard or restart Discord manually.

### Check if you have antivirus or firewall running on your computer
Sometimes antivirus programs and firewalls are blocking applications which are creating/hosting servers or just connecting to the internet. We are using a local server to receive and pass data between our app and extension, so if you will block app's ability to pass data you probably will not be able to use PreMiD.

### Tiltsd le a bővítményeket
Tilts le minden bővítményt és ellenőrizd, hogy működik-e. Ha igen, próbáld meg -lépésről-lépésre- a bővítményeket engedélyezni és írd meg nekünk, hogy melyik bővítmény blokkolta a PreMiD-et a működésben.

### Indítsd újra a számítógépet
Azt remélem azért tudod, hogy hogyan kell egy számítógépet újraindítani.

### Telepítsd újra a PreMiD alkalmazást
Néha a fájlokkal nincs valami rendben... Telepítési útmutatót [itt](/install) találod.

### Kézi eltávolítás
Windows: Write `%appdata%` on the file explorer and delete the `PreMiD` folder. MacOS: `~/users/USER/~Library/Application Support/` and delete the `PreMiD` folder.

### McAfee detected PreMiD as virus (Windows)
This is a false positive from McAfee and we have reported the issue to them, for now you can exclude PreMiD from the scan by doing the following steps:

> If you do not feel confident taking these steps, feel free to make a ticket in [#support](https://discord.premid.app/) and one of our Support Agents will be able to help you out! 
> 
> {.is-warning}

1. Open the McAfee application and click the settings icon in the top right. <img src="https://i.imgur.com/rPLZn6c.png" width="500px" style="max-width:100%;" />
2. Click "Quarantined Items" (Second from the top).
3. Expand it, and click the `>` icon before an item with the name "settings.dat".
4. Make sure the path includes "AppData\Local\Temp\PreMiD", if so select it and press restore. <img src="https://i.imgur.com/9nvHmiI.png" width="500px" style="max-width:100%;" />
5. After it is restored you can close the "Quarantined Items" popup, then press the settings icon again in the top right.
6. Click "Real-Time Scanning" (Third from the top).
7. Expand it and click "Add file".
8. Type "%appdata%" in the address bar of the File Explorer and press Enter. <img src="https://i.imgur.com/2bchwLe.png" width="500px" style="max-width:100%;" />
9. Open the "PreMiD" folder and select the "PreMiD.exe" file and click open. <img src="https://i.imgur.com/aHOyv3V.png" width="500px" style="max-width:100%;" />
10. McAfee should now ignore our file, just launch our application and you should be good to go.

### PreMiD status bugged on discord!
Ne aggódj. Press the <kbd>CTRL+R</kbd> (Windows) or <kbd>CMD+R</kbd> (MacOS) keybind while focused on your discord window to reload it.

<a name="linux"></a>

# Linux hibaelhárítás
### Ubuntu/Debian based distros
If you have downloaded Discord through Snapcraft, RPC will not work. You have to uninstall the Snapcraft version by executing `sudo snap remove discord` on a terminal, download **[Discord's Linux build](https://discordapp.com/api/download?platform=linux)** (**[or Discord Canary](https://discordapp.com/api/canary/download?platform=linux)**), then navigating to the directory you downloaded Discord to (usually `$HOME/Downloads`), then installing the package using `sudo dpkg -i discord-*.deb`. If AppImage doesn't work, you should consider checking our other packages by **[this link](https://packagecloud.io/premid/linux)**.

### Arch Linux based distros
Arch Linux based distros should use AUR (Arch User Repository) package that is named <code>premid</code> or <code>premid-git</code> (<em x-id="3">WARNING: This repository builds premid from our source code.</em>). If you don't want to install an AUR manager (yay etc.), you can check out our AppImage that is downloadable from our <strong x-id="1"><a href="https://github.com/premid/linux/releases">Linux repository</a></strong>.
<em x-id="3">Warning: the package in the <strong x-id="1">AUR</strong> repository is not maintained by us (as PreMiD organization), but by other people.</em>

### Port binding
You should know that <strong x-id="1">PreMiD</strong> binds itself to the port <strong x-id="1">3020</strong>. This is necessary for the Extension and the Application communicate. If <strong x-id="1">PreMiD</strong> shows you an error about this port, you should check if something is binded to the 3020 port by running <code>sudo lsof -i:3020</code> or <code>sudo netstat -tnlp | grep :3020</code> in your terminal. If some process is binded to it you should make sure to free the port and try running <code>PreMiD</code> again.

### PreMiD's AppImage doesn't launch at login
As we stated in our **Linux repository**, AppImage can't be launched at login. You can add it to autostart manually by doing these steps:
1. Make a file named <strong x-id="1">rc.local</strong> in the <code>/etc</code> directory.
2. Open this file in your favourite editor and paste given code with changing some things:
```bash
#!/bin/bash
# Required to run as /bin/bash (if you use zsh etc. you can change it.)

# Example: /home/PreMiD/PreMiD*.AppImage
<directory to appimage>/PreMiD*.AppImage

exit 0
```
3. Save file and chmod it as executable `sudo chmod a+x /etc/rc.local`.
4. Restart your PC and PreMiD AppImage should launch at login.

<a name="macos"></a>

# MacOS hibaelhárítás
### Error creating directory
<img src="https://i.imgur.com/td92lf6.png" width="300px" style="max-width:100%;" />

If you get this error, it means that your account doesn't have Administrator permissions and you need to create folder manually by doing these steps:
1. Open finder and open **Applications** folder.
2. Right-click on blank space and click **Create folder**.
3. To this folder assign `PreMiD` name (remember about upper-cased letters).
4. Open installer again.

# Ez nem oldotta meg a problémát
Please open a ticket in [#support](https://discord.premid.app/).
