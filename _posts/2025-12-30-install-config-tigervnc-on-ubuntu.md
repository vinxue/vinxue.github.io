---
layout: post
title: Install and Configure TigerVNC on Ubuntu
feature-img: "assets/img/pexels/desk-music.jpg"
thumbnail: "assets/img/pexels/desk-music.jpg"
author: vinxue
tags: [Linux]
---

## Install and Configure TigerVNC on Ubuntu

The guide demonstrates how to set up a VNC desktop sharing environment on Ubuntu using TigerVNC. The instructions are applicable to Ubuntu 22.04.x and 24.04.x.

### Install TigerVNC Package
Install the TigerVNC server package using the terminal.
```bash
sudo apt install tigervnc-standalone-server
```

### Set VNC Password
Run `vncpasswd` to create a password for VNC session following the prompts.
```bash
vncpasswd
```

### Configure TigerVNC Startup Script
Create or edit the TigerVNC configuration script `~/.vnc/config`.
```bash
session=ubuntu
localhost=no
```

### Start VNC Server
Start the VNC serve with:
```bash
vncserver
```

### NOTE
- **MUST log out** Ubuntu account before connect this Ubuntu from another compute.
- Set Ubuntu `Settings` -> `Power` -> `Screen Blank` to `Never`.
- Unlock login session by `sudo loginctl unlock-session` if lock screen is frozen or unresponsive.
