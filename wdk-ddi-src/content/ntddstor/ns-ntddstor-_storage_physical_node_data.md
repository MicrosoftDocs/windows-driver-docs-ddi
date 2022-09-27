---
UID: NS:ntddstor._STORAGE_PHYSICAL_NODE_DATA
title: STORAGE_PHYSICAL_NODE_DATA (ntddstor.h)
description: Specifies the physical device data of a storage node.
old-location: storage\storage_physical_node_data.htm
tech.root: storage
ms.date: 08/18/2022
keywords: ["STORAGE_PHYSICAL_NODE_DATA structure"]
ms.keywords: "*PSTORAGE_PHYSICAL_NODE_DATA, PSTORAGE_PHYSICAL_NODE_DATA, PSTORAGE_PHYSICAL_NODE_DATA structure pointer [Storage Devices], STORAGE_PHYSICAL_NODE_DATA, STORAGE_PHYSICAL_NODE_DATA structure [Storage Devices], _STORAGE_PHYSICAL_NODE_DATA, ntddstor/PSTORAGE_PHYSICAL_NODE_DATA, ntddstor/STORAGE_PHYSICAL_NODE_DATA, storage.storage_physical_node_data"
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
targetos: Windows
req.typenames: STORAGE_PHYSICAL_NODE_DATA, *PSTORAGE_PHYSICAL_NODE_DATA
f1_keywords:
 - _STORAGE_PHYSICAL_NODE_DATA
 - ntddstor/_STORAGE_PHYSICAL_NODE_DATA
 - PSTORAGE_PHYSICAL_NODE_DATA
 - ntddstor/PSTORAGE_PHYSICAL_NODE_DATA
 - STORAGE_PHYSICAL_NODE_DATA
 - ntddstor/STORAGE_PHYSICAL_NODE_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddstor.h
api_name:
 - _STORAGE_PHYSICAL_NODE_DATA
 - PSTORAGE_PHYSICAL_NODE_DATA
 - STORAGE_PHYSICAL_NODE_DATA
---

# STORAGE_PHYSICAL_NODE_DATA structure

## -description

Specifies the physical device data of a storage node.

## -struct-fields

### -field NodeId

The hardware ID of the storage node.

### -field AdapterCount

A value of 0 or 1 that indicates the adapter count in the storage node.

### -field AdapterDataLength

The data length of the storage adapter in the storage node, in units of kilobytes (1024 bytes).

### -field AdapterDataOffset

The data offset from the beginning of the data structure. The buffer contains an array of [**STORAGE_PHYSICAL_ADAPTER_DATA**](ns-ntddstor-_storage_physical_adapter_data.md).

### -field DeviceCount

A value equal to or greater than 1 that indicates the device count in the storage node.

### -field DeviceDataLength

The data length of the storage device in the storage node, in units of kilobytes (1024 bytes).

### -field DeviceDataOffset

The data offset from the beginning of the data structure. The buffer contains an array of [**STORAGE_PHYSICAL_DEVICE_DATA**](ns-ntddstor-_storage_physical_device_data.md).

### -field Reserved[3]

Reserved; do not use.

## -see-also

[**STORAGE_PHYSICAL_TOPOLOGY_DESCRIPTOR**](ns-ntddstor-_storage_physical_topology_descriptor.md)
