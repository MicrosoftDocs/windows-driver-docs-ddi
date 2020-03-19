---
UID: NS:mpiowmi._MPIO_DISK_HEALTH_INFO
title: _MPIO_DISK_HEALTH_INFO (mpiowmi.h)
description: The MPIO_DISK_HEALTH_INFO structure is used to query the available health information for every multi-path disk in the system.
old-location: storage\mpio_disk_health_info.htm
tech.root: storage
ms.assetid: 20813e29-907f-42b0-9229-a9ef78f46e1d
ms.date: 03/29/2018
keywords: ["_MPIO_DISK_HEALTH_INFO structure"]
ms.keywords: "*PMPIO_DISK_HEALTH_INFO, MPIO_DISK_HEALTH_INFO, MPIO_DISK_HEALTH_INFO structure [Storage Devices], PMPIO_DISK_HEALTH_INFO, PMPIO_DISK_HEALTH_INFO structure pointer [Storage Devices], _MPIO_DISK_HEALTH_INFO, mpiowmi/MPIO_DISK_HEALTH_INFO, mpiowmi/PMPIO_DISK_HEALTH_INFO, storage.mpio_disk_health_info, structs-scsibus_d802e57e-d591-4a38-809c-0e8a1ae84eea.xml"
f1_keywords:
 - "mpiowmi/MPIO_DISK_HEALTH_INFO"
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
- MPIO_DISK_HEALTH_INFO
product:
- Windows
targetos: Windows
req.typenames: MPIO_DISK_HEALTH_INFO, *PMPIO_DISK_HEALTH_INFO
---

# _MPIO_DISK_HEALTH_INFO structure


## -description


The MPIO_DISK_HEALTH_INFO structure is used to query the available health information for every multi-path disk in the system.


## -struct-fields




### -field NumberDiskPackets

An unsigned 32-bitfield that returns the number of available health packets that correspond to the number of multi-path disks under MPIO control.


### -field Reserved

Should be zero.


### -field DiskHealthPackets

An array of health information packets for all the available multi-path disks under MPIO control. The number of elements in the array is given by NumberDiskPackets, and each element of the array is an instance of an MPIO_DISK_HEALTH_CLASS structure.

