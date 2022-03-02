---
layout: post
title: Install OS by QEMU
feature-img: "assets/img/pexels/computer2.jpg"
thumbnail: "assets/img/pexels/computer2.jpg"
author: vinxue
tags: [UEFI]
---

## Install OS by QEMU

1. Download QEMU installation package from [QEMU](https://www.qemu.org/download/).

2. Create a virtual disk with RAW format
```
qemu-img create -f raw Win10-qemu.img 15G
```

3. Install OS (Windows 10 as an example) by below command
```
qemu-system-x86_64.exe -pflash OVMF.fd -serial file:bios.log -hda Win10-qemu.img -boot d -cdrom Win10_21H2_English_x64.iso -smp 4 -m 4096
```

if use QEMU with RTL8139 network adaptor
```
qemu-system-x86_64.exe -pflash OVMF.fd -serial file:bios.log -hda Win10-qemu.img -boot d -cdrom Win10_21H2_English_x64.iso -smp 4 -m 4096 -netdev user,id=n0 -device rtl8139,netdev=n0
```

Addition QEMU command for UEFI boot
```
qemu-system-x86_64.exe -pflash OVMF.fd -serial stdio / file:bios.log -hda fat:rw:<WORKSPACE>
qemu-system-x86_64.exe -pflash OVMF.fd -serial file:bios.log -hda fat:rw:C:\Work\OVMF
```
