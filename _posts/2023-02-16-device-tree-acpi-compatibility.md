---
layout: post
title: Device Tree and ACPI Compatibility on x86
feature-img: "assets/img/pexels/desk-music.jpg"
thumbnail: "assets/img/pexels/desk-music.jpg"
author: vinxue
tags: [UEFI]
---

## Device Tree and ACPI Compatibility on x86

The Device Tree protocol uses device identification based on the "compatible" property whose value is a string or an array of strings recognized as device identifiers by Linux drivers and the driver core.

In ACPI, it alos provides a special DT namespace link device ID (PRP0001) to use the existing DT-compatible device identification.

- An ACPI sample code as below:

```c
  Device (TMP0)
  {
    Name (_HID, "PRP0001")
    Name (_UID, 0x0)

    Name (_DSD, Package () {
      ToUUID ("daffd814-6eba-4d8c-8a91-bc9bbf4aa301"),
      Package () {
        Package () {"compatible", "snps,dw-apb-ssi"},
      }
    })

    Method (_CRS, 0, Serialized)
    {
      Name (SBUF, ResourceTemplate ()
      {
        Interrupt (ResourceConsumer, Level, ActiveHigh, Exclusive,,,) {32}
        Memory32Fixed (ReadWrite, 0xE0000000, 0x1000)
      })
      Return (SBUF)
    }
  }
```

- Linux config change

Select CONFIG_OF configuration

```
menuconfig OF
  bool "Device Tree and Open Firmware support"
  help
    This option enables the device tree infrastructure.
    It is automatically selected by platforms that need it or can
    be enabled manually for unittests, overlays or
    compile-coverage.
```

Refer to Documentation\firmware-guide\acpi\enumeration.rst for more details.
