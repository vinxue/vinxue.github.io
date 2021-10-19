---
layout: post
title: Repo Support in Windows by Cygwin
feature-img: "assets/img/pexels/search-map.jpeg"
thumbnail: "assets/img/pexels/search-map.jpeg"
author: vinxue
tags: [Essay]
---

## Repo Support in Windows by Cygwin

Repo is a tool built on top of Git and developed by Google. Repo helps manage many Git repositories, does the uploads to revision control systems, and automates parts of the development workflow.

Unfortunately, Repo is primarily developed on Linux, Windows is not fully support and it is a bit difficult to configure.

To help the Repo setting in Windows, there is a simple instruction.

OS Version: Windows 10 or newer.

1. Install Cygwin from [https://www.cygwin.com/](https://www.cygwin.com/). Select a server and instll Python3 and Git.
2. Set up your SSH Key or ~/.ssh/config per your project.
3. Download [Repo](https://storage.googleapis.com/git-repo-downloads/repo) from [https://gerrit.googlesource.com/git-repo/](https://gerrit.googlesource.com/git-repo/). It's a single script. Copy the `repo` script to Cygwin installation directory (e.g. C:\cygwin64\bin)
4. Set Sysmlink for Windows.

    Repo will use symlinks heavily internally. On *NIX platforms, this isn't an issue, but Windows makes it a bit difficult.

    > a. Add below 1 line in `C:\cygwin64\home\<user>\.bashrc`

    ```bash
    # User dependent .bashrc file
    export CYGWIN=winsymlinks:native
    ```

    > b. Edit Group Policy (run `gpedit.msc`)

    Local Computer Policy -> Windows Settings -> Security Settings -> Local Policies -> User Rights Assignment -> Create symbolic links ->Add User or Group
5. Set correct filesystem permission in `C:\cygwin64\etc\fstab`
   ```bash
   none /cygdrive cygdrive binary,posix=0,user,noacl 0 0
   ```
6. (Optional) Set CRLF for Winodws:
   ```
   git config --global core.autocrlf true
   ```
