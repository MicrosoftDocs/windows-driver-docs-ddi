---
UID: NS:ntddstor._STORAGE_PHYSICAL_NODE_DATA
title: "_STORAGE_PHYSICAL_NODE_DATA"
author: windows-driver-content
description: Specifies the physical device data of a storage node.
old-location: storage\storage_physical_node_data.htm
tech.root: storage
ms.assetid: F6C1EE86-FB1C-467D-9E03-B238CB132D1A
ms.date: 03/29/2018
ms.keywords: "*PSTORAGE_PHYSICAL_NODE_DATA, PSTORAGE_PHYSICAL_NODE_DATA, PSTORAGE_PHYSICAL_NODE_DATA structure pointer [Storage Devices], STORAGE_PHYSICAL_NODE_DATA, STORAGE_PHYSICAL_NODE_DATA structure [Storage Devices], _STORAGE_PHYSICAL_NODE_DATA, ntddstor/PSTORAGE_PHYSICAL_NODE_DATA, ntddstor/STORAGE_PHYSICAL_NODE_DATA, storage.storage_physical_node_data"
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
-	STORAGE_PHYSICAL_NODE_DATA
product:
- Windows
targetos: Windows
req.typenames: STORAGE_PHYSICAL_NODE_DATA, *PSTORAGE_PHYSICAL_NODE_DATA
---

# _STORAGE_PHYSICAL_NODE_DATA structure


## -description


Specifies the physical device data of a storage node.


## -struct-fields




### -field NodeId

The hardware ID of the storage node.


### -field AdapterCount

A value of 0 or 1 that indicates the adapter count in the storage node.


### -field AdapterDataLength

The data length of the storage adapter in the storage node,  in units of kilobytes (1024 bytes).


### -field AdapterDataOffset

The data offset from the beginning of the data structure. The buffer contains an array of <a href="https://msdn.microsoft.com/library/windows/hardware/mt653959">STORAGE_PHYSICAL_ADAPTER_DATA</a>.


### -field DeviceCount

A value less than or equal to 1.


### -field DeviceDataLength

The data length of the storage device in the storage node,  in units of kilobytes (1024 bytes).


### -field DeviceDataOffset

The data offset from the beginning of the data structure. The buffer contains an array of <a href="https://msdn.microsoft.com/library/windows/hardware/mt653960">STORAGE_PHYSICAL_DEVICE_DATA</a>.


### -field Reserved

 




#### - Reserved[3]

Specifies if the storage adapter is reserved.

