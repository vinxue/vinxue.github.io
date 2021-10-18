---
layout: post
title: VS Code setting of UEFI
feature-img: "assets/img/pexels/desk.jpg"
thumbnail: "assets/img/pexels/desk.jpg"
author: vinxue
tags: [UEFI]
---

## VS Code setting of UEFI

The VS Code setting script:

```json
{
    "files.exclude": {
        "**/.vscode":true,
        "**/Build": true,
        "**/.repo": true
    },
    "C_Cpp.default.browse.databaseFilename": "${workspaceFolder}/.vscode/.BROWSE.VC.DB",
    "C_Cpp.intelliSenseCachePath": "${workspaceFolder}/.vscode",
    "C_Cpp.errorSquiggles": "Disabled",
    "editor.renderWhitespace": "all",
    "editor.guides.indentation": false,
    "editor.tabSize": 2,
    "files.trimTrailingWhitespace": true,
    "terminal.integrated.defaultProfile.windows": "Command Prompt",
    "C_Cpp.dimInactiveRegions": false,
    "editor.renderControlCharacters": true,
    "workbench.editor.showTabs": true,
    "files.associations": {
        "*.dec": "makefile",
        "*.dsc": "makefile",
        "*.fdf": "makefile",
        "*.asl": "c",
        "*.aslc": "c",
        "*.act": "c",
        "*.inf": "makefile"
    },
    "security.workspace.trust.enabled": false
}
```