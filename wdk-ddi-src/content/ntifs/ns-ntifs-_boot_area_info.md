---
UID: NS:ntifs._BOOT_AREA_INFO
title: _BOOT_AREA_INFO (ntifs.h)
description: The BOOT_AREA_INFO structure contains the output for the FSCTL_GET_BOOT_AREA_INFO control code.
old-location: ifsk\boot_area_info.htm
tech.root: ifsk
ms.assetid: 9f092940-b8be-4d28-b82c-d169abefe5d9
ms.date: 04/16/2018
keywords: ["BOOT_AREA_INFO structure"]
ms.keywords: "*PBOOT_AREA_INFO, BOOT_AREA_INFO, BOOT_AREA_INFO structure [Installable File System Drivers], PBOOT_AREA_INFO, PBOOT_AREA_INFO structure pointer [Installable File System Drivers], _BOOT_AREA_INFO, ifsk.boot_area_info, ntifs/BOOT_AREA_INFO, ntifs/PBOOT_AREA_INFO"
f1_keywords:
 - "ntifs/BOOT_AREA_INFO"
 - "BOOT_AREA_INFO"
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows Server 2008 R2, Windows 7
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntifs.h
api_name:
- BOOT_AREA_INFO
targetos: Windows
req.typenames: BOOT_AREA_INFO, *PBOOT_AREA_INFO
---

# _BOOT_AREA_INFO structure


## -description


The <b>BOOT_AREA_INFO</b> structure contains the output for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-get-boot-area-info">FSCTL_GET_BOOT_AREA_INFO</a> control code.


## -struct-fields




### -field BootSectorCount

The number of elements in the <b>BootSectors</b> array.


### -field Offset

 


### -field BootSectors

A variable length array of structures. Each structure contains an <b>Offset</b> member.



#### Offset

The location of a boot sector or a copy of a boot sector.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-get-boot-area-info">FSCTL_GET_BOOT_AREA_INFO</a>
 

 

