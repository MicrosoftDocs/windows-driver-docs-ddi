---
UID: NS:wdm._BOOTDISK_INFORMATION
title: _BOOTDISK_INFORMATION (wdm.h)
description: The BOOTDISK_INFORMATION structure contains basic information describing the boot and system disks.
old-location: kernel\bootdisk_information.htm
tech.root: kernel
ms.assetid: dd2a525d-fb9d-4fea-b9d7-64b1f498550c
ms.date: 04/30/2018
keywords: ["BOOTDISK_INFORMATION structure"]
ms.keywords: "*PBOOTDISK_INFORMATION, BOOTDISK_INFORMATION, BOOTDISK_INFORMATION structure [Kernel-Mode Driver Architecture], PBOOTDISK_INFORMATION, PBOOTDISK_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _BOOTDISK_INFORMATION, kernel.bootdisk_information, kstruct_a_61cd1024-0bb4-4601-a458-4bf52a2339d5.xml, wdm/BOOTDISK_INFORMATION, wdm/PBOOTDISK_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Drivers on Microsoft Windows XP and later versions of the Windows operating system should use the BOOTDISK_INFORMATION_EX structure instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: BOOTDISK_INFORMATION, *PBOOTDISK_INFORMATION
f1_keywords:
 - _BOOTDISK_INFORMATION
 - wdm/_BOOTDISK_INFORMATION
 - PBOOTDISK_INFORMATION
 - wdm/PBOOTDISK_INFORMATION
 - BOOTDISK_INFORMATION
 - wdm/BOOTDISK_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - BOOTDISK_INFORMATION
---

# _BOOTDISK_INFORMATION structure


## -description

The <b>BOOTDISK_INFORMATION</b> structure contains basic information describing the boot and system disks.

## -struct-fields

### -field BootPartitionOffset

Specifies the offset, in bytes, on the boot disk where the boot partition begins.

### -field SystemPartitionOffset

Specifies the offset, in bytes, on the system disk where the system partition begins.

### -field BootDeviceSignature

If the boot disk is formatted with an MBR partition table, this specifies the signature for the disk's MBR partition table. Otherwise, this member is unused.

### -field SystemDeviceSignature

If the system disk is formatted with an MBR partition table, this specifies the signature for the disk's MBR partition table. Otherwise, this member is unused.

## -remarks

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetbootdiskinformation">IoGetBootDiskInformation</a> returns this structure to describe the boot and system disks.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_bootdisk_information_ex">BOOTDISK_INFORMATION_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetbootdiskinformation">IoGetBootDiskInformation</a>

