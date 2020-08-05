---
UID: NS:ntddstor._STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR
title: _STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR (ntddstor.h)
description: Describes the physical topology of storage in a system.
old-location: storage\storage_physical_topology_descriptor.htm
tech.root: storage
ms.assetid: FD5714DF-9D34-4396-86BC-40054C199A0E
ms.date: 03/29/2018
keywords: ["STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR structure"]
ms.keywords: "*PSTORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, PSTORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, PSTORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR structure pointer [Storage Devices], STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR structure [Storage Devices], _STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, ntddstor/PSTORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, ntddstor/STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, storage.storage_physical_topology_descriptor"
f1_keywords:
 - "ntddstor/STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR"
 - "STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddstor.h
api_name:
- STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR
targetos: Windows
req.typenames: STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR, *PSTORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR
---

# _STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR structure


## -description

The **STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR** structure describes the physical topology of a device or adapter.


## -struct-fields


### -field Version

Version of this structure, in bytes. The value of this member will change as members are added to the structure. Set to **sizeof**(STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR).

### -field Size

Total size of the data, in bytes, which may include data that follows this structure. Should be >= **sizeof**(STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR).

### -field NodeCount

Total number of storage nodes in the system.


### -field Reserved

Reserved for future use. Do not use.

### -field Node

Array of [STORAGE_PHYSICAL_NODE_DATA](ns-ntddstor-_storage_physical_node_data.md) structures that describe the physical device data of each storage node. The number of structures in the array is determined by *NodeCount*.


## -remarks

The STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR structure is returned from an [IOCTL_STORAGE_QUERY_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property) request that has a **PropertyId** of StorageAdapterPhysicalTopologyProperty or StorageDevicePhysicalTopologyProperty. 

## -see-also

[IOCTL_STORAGE_QUERY_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property)

[STORAGE_PHYSICAL_NODE_DATA](ns-ntddstor-_storage_physical_node_data.md)
