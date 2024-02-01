---
layout: post
title: EDK II Code Formatting
feature-img: "assets/img/pexels/computer2.jpg"
thumbnail: "assets/img/pexels/computer2.jpg"
author: vinxue
tags: [UEFI]
---

## EDK II Code Formatting

- Install the Uncrustify VS Code extension: Search **Uncrustify** in VS Code Marketplace and Install it

![Uncrustify](/assets/img/postimg/uncrustify.png)

- Extract **[uncrustify.exe and uncrustify.cfg](/assets/postdata/Uncrustify.zip)** to C:\Uncrustify

- Configure the Uncrustify plugin for your local setup by adding the following to your VS Code

```bash
"uncrustify.configPath.windows": "C:/Uncrustify/uncrustify.cfg",
"uncrustify.executablePath.windows": "C:/Uncrustify/uncrustify.exe"
```

- Open a C source code file, *Ctrl+Shift+P -> Format Document With... -> Configure Default Formatter -> Uncrustify*

- Then, *Ctrl+Shift+P -> Format Document* any time you would like to format your source code file with Uncrustify

## Reference
[EDK II Code Formatting · tianocore/tianocore.github.io Wiki](https://github.com/tianocore/tianocore.github.io/wiki/EDK-II-Code-Formatting)