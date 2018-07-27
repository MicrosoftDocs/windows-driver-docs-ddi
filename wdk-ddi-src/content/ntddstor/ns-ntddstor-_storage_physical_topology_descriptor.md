---
UID: NS:ntddstor._STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR
title: "_STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR"
author: windows-driver-content
description: Describes the physical topology of storage in a system.
old-location: storage\storage_physical_topology_descriptor.htm
tech.root: storage
ms.assetid: FD5714DF-9D34-4396-86BC-40054C199A0E
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSTORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, PSTORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, PSTORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR structure pointer [Storage Devices], STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR structure [Storage Devices], _STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, ntddstor/PSTORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, ntddstor/STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, storage.storage_physical_topology_descriptor"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddstor.h
api_name:
-	STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, *PSTORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR
---

# _STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR structure


## -description


Describes the physical topology of storage in a system.


## -struct-fields




### -field Version

The version of the physical topology.


### -field Size

The total size of data in the system.


### -field NodeCount

The total number of storage nodes in the system.


### -field Reserved

Indicates if storage in the system is reserved.


### -field Node

 




#### - Node[ANYSIZE_ARRAY]

Describes the storage nodes in the system.

