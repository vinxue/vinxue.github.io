---
layout: post
title: OVMF UEFI with Built-in ACPI Table
feature-img: "assets/img/pexels/desk-music.jpg"
thumbnail: "assets/img/pexels/desk-music.jpg"
author: vinxue
tags: [UEFI]
---

## OVMF UEFI with Built-in ACPI Table

Current QEMU composes all ACPI tables on the host side, according to the target hardware configuration, and make the tables available to any guest firmware over fw_cfg. OVMF UEFI also removed built-in ACPI table.

To enable built-in ACPI table in current EDK2 code, need to revert to an old version.

- Checkout an old edk2 branch (edk2-stable202105)
```
git clone --recurse-submodules https://github.com/tianocore/edk2.git
cd edk2
git checkout edk2-stable202105
```

- Change some code

```c
//
// OvmfPkg/AcpiPlatformDxe/AcpiPlatform.c
//

EFI_STATUS
EFIAPI
InstallOvmfFvTables (
  IN  EFI_ACPI_TABLE_PROTOCOL     *AcpiTable
  )
{
  EFI_STATUS                           Status;
  EFI_FIRMWARE_VOLUME2_PROTOCOL        *FwVol;
  INTN                                 Instance;
  EFI_ACPI_COMMON_HEADER               *CurrentTable;
  UINTN                                TableHandle;
  UINT32                               FvStatus;
  UINTN                                TableSize;
  UINTN                                Size;
  EFI_ACPI_TABLE_INSTALL_ACPI_TABLE    TableInstallFunction;

  Instance     = 0;
  CurrentTable = NULL;
  TableHandle  = 0;

  // if (QemuDetected ()) {
    TableInstallFunction = QemuInstallAcpiTable;
  // } else {
    // TableInstallFunction = InstallAcpiTable;
  // }

EFI_STATUS
EFIAPI
InstallAcpiTables (
  IN   EFI_ACPI_TABLE_PROTOCOL       *AcpiTable
  )
{
  EFI_STATUS                         Status;

  // if (XenDetected ()) {
  //   Status = InstallXenTables (AcpiTable);
  // } else {
  //   Status = InstallQemuFwCfgTables (AcpiTable);
  // }

  // if (EFI_ERROR (Status)) {
    Status = InstallOvmfFvTables (AcpiTable);
  // }

  return Status;
}
```

- Build OVMF BIOS

```
build -a IA32 -a X64 -p OvmfPkg\OvmfPkgIa32X64.dsc -t VS2019 -b DEBUG -D DEBUG_ON_SERIAL_PORT
```
