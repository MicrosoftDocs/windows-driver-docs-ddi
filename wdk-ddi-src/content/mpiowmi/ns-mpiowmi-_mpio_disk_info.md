---
UID: NS:mpiowmi._MPIO_DISK_INFO
title: _MPIO_DISK_INFO (mpiowmi.h)
description: The MPIO_DISK_INFO structure allows applications to query the system for the top level view of its disk topology. The request must be directed to the MPIO control object by using its WMI instance name.
old-location: storage\mpio_disk_info.htm
tech.root: storage
ms.assetid: edefb7f5-f423-48cc-81c9-16153c228d45
ms.date: 03/29/2018
keywords: ["MPIO_DISK_INFO structure"]
ms.keywords: "*PMPIO_DISK_INFO, MPIO_DISK_INFO, MPIO_DISK_INFO structure [Storage Devices], PMPIO_DISK_INFO, PMPIO_DISK_INFO structure pointer [Storage Devices], _MPIO_DISK_INFO, mpiowmi/MPIO_DISK_INFO, mpiowmi/PMPIO_DISK_INFO, storage.mpio_disk_info, structs-scsibus_d58f08a1-1534-4f93-83d4-031ce1dee9bf.xml"
f1_keywords:
 - "mpiowmi/MPIO_DISK_INFO"
 - "MPIO_DISK_INFO"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- mpiowmi.h
api_name:
- MPIO_DISK_INFO
targetos: Windows
req.typenames: MPIO_DISK_INFO, *PMPIO_DISK_INFO
---

# _MPIO_DISK_INFO structure


## -description


The MPIO_DISK_INFO structure allows applications to query the system for the top level view of its disk topology. The request must be directed to the MPIO control object by using its WMI instance name.


## -struct-fields




### -field NumberDrives

An unsigned 32-bitfield that represents the number of multi-path disks in the system.


### -field DriveInfo

An array that returns the information representing each multi-path LUN (pseudo-LUN) in the system. The number of elements in the array is given by <i>NumberDrives</i> and each element represents an instance of an MPIO_DRIVE_INFO structure.

