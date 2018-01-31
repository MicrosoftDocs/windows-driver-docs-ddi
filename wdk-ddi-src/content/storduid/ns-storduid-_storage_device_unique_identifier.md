---
UID: NS:storduid._STORAGE_DEVICE_UNIQUE_IDENTIFIER
title: "_STORAGE_DEVICE_UNIQUE_IDENTIFIER"
author: windows-driver-content
description: The STORAGE_DEVICE_UNIQUE_IDENTIFIER structure defines a device unique identifier (DUID).
old-location: storage\storage_device_unique_identifier.htm
old-project: storage
ms.assetid: 02de3382-031a-4d42-b349-786248da9c5c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: structs-general_ed4e22dc-a5cb-4746-a846-cbae5e8d7ce8.xml, STORAGE_DEVICE_UNIQUE_IDENTIFIER, storduid/PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, storduid/STORAGE_DEVICE_UNIQUE_IDENTIFIER, PSTORAGE_DEVICE_UNIQUE_IDENTIFIER structure pointer [Storage Devices], STORAGE_DEVICE_UNIQUE_IDENTIFIER structure [Storage Devices], _STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, storage.storage_device_unique_identifier, PSTORAGE_DEVICE_UNIQUE_IDENTIFIER
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storduid.h
apiname:
-	STORAGE_DEVICE_UNIQUE_IDENTIFIER
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER"
req.product: Windows 10 or later.
---

# _STORAGE_DEVICE_UNIQUE_IDENTIFIER structure


## -description


The STORAGE_DEVICE_UNIQUE_IDENTIFIER structure defines a device unique identifier (DUID).


## -syntax


````
typedef struct _STORAGE_DEVICE_UNIQUE_IDENTIFIER {
  ULONG Version;
  ULONG Size;
  ULONG StorageDeviceIdOffset;
  ULONG StorageDeviceOffset;
  ULONG DriveLayoutSignatureOffset;
} STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER;
````


## -struct-fields




#### - Version

The version of the DUID.


#### - Size

The size, in bytes, of the identifier header and the identifiers (IDs) that follow the header.


#### - StorageDeviceIdOffset

The offset, in bytes, from the beginning of the header to the device ID descriptor (<a href="..\ntddstor\ns-ntddstor-_storage_device_id_descriptor.md">STORAGE_DEVICE_ID_DESCRIPTOR</a>). The device ID descriptor contains the IDs that are extracted from page 0x83 of the device's vital product data (VPD).


#### - StorageDeviceOffset

The offset, in bytes, from the beginning of the header to the device descriptor (<a href="..\ntddstor\ns-ntddstor-_storage_device_descriptor.md">STORAGE_DEVICE_DESCRIPTOR</a>). The device descriptor contains IDs that are extracted from non-VPD inquiry data.


#### - DriveLayoutSignatureOffset

The offset, in bytes, to the drive layout signature (<a href="..\storduid\ns-storduid-_storage_device_layout_signature.md">STORAGE_DEVICE_LAYOUT_SIGNATURE</a>).


## -see-also

<a href="..\ntddstor\ns-ntddstor-_storage_device_id_descriptor.md">STORAGE_DEVICE_ID_DESCRIPTOR</a>

<a href="..\ntddstor\ns-ntddstor-_storage_device_descriptor.md">STORAGE_DEVICE_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_DEVICE_UNIQUE_IDENTIFIER structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

