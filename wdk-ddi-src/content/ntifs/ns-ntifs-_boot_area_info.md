---
UID: NS:ntifs._BOOT_AREA_INFO
title: "_BOOT_AREA_INFO"
author: windows-driver-content
description: The BOOT_AREA_INFO structure contains the output for the FSCTL_GET_BOOT_AREA_INFO control code.
old-location: ifsk\boot_area_info.htm
old-project: ifsk
ms.assetid: 9f092940-b8be-4d28-b82c-d169abefe5d9
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PBOOT_AREA_INFO, ntifs/PBOOT_AREA_INFO, BOOT_AREA_INFO structure [Installable File System Drivers], ntifs/BOOT_AREA_INFO, _BOOT_AREA_INFO, *PBOOT_AREA_INFO, ifsk.boot_area_info, BOOT_AREA_INFO, PBOOT_AREA_INFO structure pointer [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntifs.h
apiname:
-	BOOT_AREA_INFO
product: Windows
targetos: Windows
req.typenames: BOOT_AREA_INFO, *PBOOT_AREA_INFO
---

# _BOOT_AREA_INFO structure


## -description


The <b>BOOT_AREA_INFO</b> structure contains the output for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff728858">FSCTL_GET_BOOT_AREA_INFO</a> control code.


## -syntax


````
typedef struct _BOOT_AREA_INFO {
  ULONG  BootSectorCount;
  struct {
    LARGE_INTEGER Offset;
  } BootSectors[2];
} BOOT_AREA_INFO, *PBOOT_AREA_INFO;
````


## -struct-fields




### -field Offset

 


#### - BootSectors

A variable length array of structures. Each structure contains an <b>Offset</b> member.


#### Offset

The location of a boot sector or a copy of a boot sector.


#### - BootSectorCount

The number of elements in the <b>BootSectors</b> array.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff728858">FSCTL_GET_BOOT_AREA_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20BOOT_AREA_INFO structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

