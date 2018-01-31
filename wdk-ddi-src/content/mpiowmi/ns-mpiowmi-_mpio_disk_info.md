---
UID: NS:mpiowmi._MPIO_DISK_INFO
title: "_MPIO_DISK_INFO"
author: windows-driver-content
description: The MPIO_DISK_INFO structure allows applications to query the system for the top level view of its disk topology. The request must be directed to the MPIO control object by using its WMI instance name.
old-location: storage\mpio_disk_info.htm
old-project: storage
ms.assetid: edefb7f5-f423-48cc-81c9-16153c228d45
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: mpiowmi/MPIO_DISK_INFO, structs-scsibus_d58f08a1-1534-4f93-83d4-031ce1dee9bf.xml, MPIO_DISK_INFO, storage.mpio_disk_info, PMPIO_DISK_INFO structure pointer [Storage Devices], _MPIO_DISK_INFO, PMPIO_DISK_INFO, *PMPIO_DISK_INFO, mpiowmi/PMPIO_DISK_INFO, MPIO_DISK_INFO structure [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	mpiowmi.h
apiname:
-	MPIO_DISK_INFO
product: Windows
targetos: Windows
req.typenames: MPIO_DISK_INFO, *PMPIO_DISK_INFO
---

# _MPIO_DISK_INFO structure


## -description


The MPIO_DISK_INFO structure allows applications to query the system for the top level view of its disk topology. The request must be directed to the MPIO control object by using its WMI instance name.


## -syntax


````
typedef struct _MPIO_DISK_INFO {
  ULONG           NumberDrives;
  MPIO_DRIVE_INFO DriveInfo[1];
} MPIO_DISK_INFO, *PMPIO_DISK_INFO;
````


## -struct-fields




#### - NumberDrives

An unsigned 32-bitfield that represents the number of multi-path disks in the system.


#### - DriveInfo

An array that returns the information representing each multi-path LUN (pseudo-LUN) in the system. The number of elements in the array is given by <i>NumberDrives</i> and each element represents an instance of an MPIO_DRIVE_INFO structure.

