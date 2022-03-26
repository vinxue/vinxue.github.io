---
layout: post
title: Splitting a directory out to a standalone repository
feature-img: "assets/img/pexels/teach.jpg"
thumbnail: "assets/img/pexels/teach.jpg"
author: vinxue
tags: [Essay]
---

## Splitting a directory out to a standalone repository

This article explains a way how to split a directory out to a new Git repository.

### Current Code Structure (Windows Environment)
```bash
├─UefiToolkitPkg
   ├─Application  # This is should be a standalone repository
   ├─Drivers
   ├─Include
   ├─Library
   ├─Tools
   └─...
```

### Solution
- Splitting "Application" directory to a Git repository.
```bash
cd UefiToolkitPkg
git subtree split -P Application -b Application
```

```bash
mkdir ..\Application
cd ..\Application
git init
```

```bash
git pull ..\UefiToolkitPkg Application
```

- Cleanup unnecessary files and optimize the local repository.
```bash
git gc --aggressive --prune=now
```

- Push to remote Git server.
```bash
git remote add origin https://github.com/xxx/Application.git
git push -u origin master
```
