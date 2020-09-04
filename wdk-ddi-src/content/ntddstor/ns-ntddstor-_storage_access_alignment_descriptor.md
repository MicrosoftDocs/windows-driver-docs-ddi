---
UID: NS:ntddstor._STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR
title: _STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR (ntddstor.h)
description: The STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the storage access alignment descriptor data for a device.
old-location: storage\storage_access_alignment_descriptor.htm
tech.root: storage
ms.assetid: 988122bf-d7de-44a3-a059-c984bf636cd0
ms.date: 03/29/2018
keywords: ["STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure"]
ms.keywords: PSTORAGE_ACCESS_ALIGNMENT_DESCRIPTOR, PSTORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure pointer [Storage Devices], STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR, STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure [Storage Devices], _STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR, ntddstor/PSTORAGE_ACCESS_ALIGNMENT_DESCRIPTOR, ntddstor/STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR, storage.storage_access_alignment_descriptor, structs-general_191220fa-6df5-478b-b60e-af8e3f62d441.xml
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
req.typenames: STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR, PSTORAGE_ACCESS_ALIGNMENT_DESCRIPTOR
f1_keywords:
 - _STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR
 - ntddstor/_STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR
 - PSTORAGE_ACCESS_ALIGNMENT_DESCRIPTOR
 - ntddstor/PSTORAGE_ACCESS_ALIGNMENT_DESCRIPTOR
 - STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR
 - ntddstor/STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR
---

# _STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure


## -description

The STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> request to retrieve the storage access alignment descriptor data for a device.

## -struct-fields

### -field Version

Contains the size of the structure STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR. The value of this member will change as members are added to the structure.

### -field Size

Specifies the total size of the descriptor, in bytes.

### -field BytesPerCacheLine

The number of bytes in a cache line of the device.

### -field BytesOffsetForCacheAlignment

The address offset necessary for proper cache access alignment, in bytes.

### -field BytesPerLogicalSector

The number of bytes in a logical sector of the device.

### -field BytesPerPhysicalSector

The number of bytes in a physical sector of the device.

### -field BytesOffsetForSectorAlignment

The logical sector offset within the first physical sector where the first logical sector is placed, in bytes.

Example:  Offset = 3 Logical sectors


```cpp
+- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
|LBA      |X|X|X|0|1|2|3|4|5|6|7|8|9|10|11|12|13|14|15|16|17|
|- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
|Physical |               |                  |
|Sector   |      0        |        1         |         2
+- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
```

In this example, BytesOffsetForSectorAlignment = 3 * size_of_logical_sector.

## -remarks

Storage class drivers issue a device-control request with the I/O control code  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> to retrieve this structure, which contains access alignment information for data transfer operations. The structure can be retrieved either from the device object for the bus or from an FDO, which forwards the request to the underlying bus.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a>

