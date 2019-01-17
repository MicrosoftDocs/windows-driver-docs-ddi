---
UID: NS:storduid._STORAGE_DEVICE_UNIQUE_IDENTIFIER
title: "_STORAGE_DEVICE_UNIQUE_IDENTIFIER"
description: The STORAGE_DEVICE_UNIQUE_IDENTIFIER structure defines a device unique identifier (DUID).
old-location: storage\storage_device_unique_identifier.htm
tech.root: storage
ms.assetid: 02de3382-031a-4d42-b349-786248da9c5c
ms.date: 03/29/2018
ms.keywords: "*PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, PSTORAGE_DEVICE_UNIQUE_IDENTIFIER structure pointer [Storage Devices], STORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER structure [Storage Devices], _STORAGE_DEVICE_UNIQUE_IDENTIFIER, storage.storage_device_unique_identifier, storduid/PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, storduid/STORAGE_DEVICE_UNIQUE_IDENTIFIER, structs-general_ed4e22dc-a5cb-4746-a846-cbae5e8d7ce8.xml"
ms.topic: struct
req.header: storduid.h
req.include-header: Storduid.h
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
-	storduid.h
api_name:
-	STORAGE_DEVICE_UNIQUE_IDENTIFIER
product:
- Windows
targetos: Windows
req.typenames: STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER
---

# _STORAGE_DEVICE_UNIQUE_IDENTIFIER structure


## -description


The STORAGE_DEVICE_UNIQUE_IDENTIFIER structure defines a device unique identifier (DUID).


## -struct-fields




### -field Version

The version of the DUID.


### -field Size

The size, in bytes, of the identifier header and the identifiers (IDs) that follow the header.


### -field StorageDeviceIdOffset

The offset, in bytes, from the beginning of the header to the device ID descriptor (<a href="https://msdn.microsoft.com/library/windows/hardware/ff566972">STORAGE_DEVICE_ID_DESCRIPTOR</a>). The device ID descriptor contains the IDs that are extracted from page 0x83 of the device's vital product data (VPD).


### -field StorageDeviceOffset

The offset, in bytes, from the beginning of the header to the device descriptor (<a href="https://msdn.microsoft.com/library/windows/hardware/ff566971">STORAGE_DEVICE_DESCRIPTOR</a>). The device descriptor contains IDs that are extracted from non-VPD inquiry data.


### -field DriveLayoutSignatureOffset

The offset, in bytes, to the drive layout signature (<a href="https://msdn.microsoft.com/library/windows/hardware/ff566973">STORAGE_DEVICE_LAYOUT_SIGNATURE</a>).


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566971">STORAGE_DEVICE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566972">STORAGE_DEVICE_ID_DESCRIPTOR</a>
 

 

