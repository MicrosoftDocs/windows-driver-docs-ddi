---
UID: NS:ntdddisk._DISK_GEOMETRY_EX
title: _DISK_GEOMETRY_EX (ntdddisk.h)
description: The DISK_GEOMETRY_EX structure is an arbitrary-length structure composed of a DISK_GEOMETRY structure followed by a DISK_PARTITION_INFO structure followed, in turn, by a DISK_DETECTION_INFO structure.
old-location: storage\disk_geometry_ex.htm
tech.root: storage
ms.assetid: 6397c0dd-4dc7-49fa-85a7-841f6c2b30d8
ms.date: 01/06/2020
keywords: ["DISK_GEOMETRY_EX structure"]
ms.keywords: "*PDISK_GEOMETRY_EX, DISK_GEOMETRY_EX, DISK_GEOMETRY_EX structure [Storage Devices], PDISK_GEOMETRY_EX, PDISK_GEOMETRY_EX structure pointer [Storage Devices], _DISK_GEOMETRY_EX, ntdddisk/DISK_GEOMETRY_EX, ntdddisk/PDISK_GEOMETRY_EX, storage.disk_geometry_ex, structs-disk_58b543a6-c9ee-4acf-9012-6572e9e9e627.xml"
f1_keywords:
 - "ntdddisk/DISK_GEOMETRY_EX"
 - "DISK_GEOMETRY_EX"
req.header: ntdddisk.h
req.include-header: Ntdddisk.h, Ntddk.h, Ntdddisk.h
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
- ntdddisk.h
api_name:
- DISK_GEOMETRY_EX
targetos: Windows
req.typenames: DISK_GEOMETRY_EX, *PDISK_GEOMETRY_EX
---

# _DISK_GEOMETRY_EX structure

## -description

The DISK_GEOMETRY_EX structure is an arbitrary-length structure composed of a [DISK_GEOMETRY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_geometry) structure followed by a [DISK_PARTITION_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_partition_info) structure followed, in turn, by a [DISK_DETECTION_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_detection_info) structure.

## -struct-fields

### -field Geometry

See [DISK_GEOMETRY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_geometry) for a description of this member.

### -field DiskSize

Contains the size in bytes of the disk.

### -field Data

Beginning of the data block, starting with a [DISK_PARTITION_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_partition_info) structure followed by a [DISK_DETECTION_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_detection_info) structure.

## -remarks

DISK_GEOMETRY_EX is used in conjunction with the [IOCTL_DISK_GET_DRIVE_GEOMETRY_EX](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_get_drive_geometry_ex) and the [IOCTL_DISK_GET_MEDIA_TYPES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_get_media_types) IOCTLs, in order to retrieve information about the geometry of a physical disk (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).

Because the partition and detect information are not at fixed locations within the DISK_GEOMETRY_EX structure, *ntdddisk.h* provides two macros for accessing this information. Both macros take a pointer to a structure of type DISK_GEOMETRY_EX as an argument:

```cpp
#if (NTDDI_VERSION < NTDDI_WS03)
#define DiskGeometryGetPartition(Geometry)\
                        ((PDISK_PARTITION_INFO)((Geometry)+1))

#define DiskGeometryGetDetect(Geometry)\
                        ((PDISK_DETECTION_INFO)(((PBYTE)DiskGeometryGetPartition(Geometry)+\
                                        DiskGeometryGetPartition(Geometry)->SizeOfPartitionInfo)))
#else
#define DiskGeometryGetPartition(Geometry)\
                        ((PDISK_PARTITION_INFO)((Geometry)->Data))

#define DiskGeometryGetDetect(Geometry)\
                        ((PDISK_DETECTION_INFO)(((ULONG_PTR)DiskGeometryGetPartition(Geometry)+\
                                        DiskGeometryGetPartition(Geometry)->SizeOfPartitionInfo)))
#endif
```

## -see-also

[DISK_DETECTION_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_detection_info)

[DISK_GEOMETRY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_geometry)

[DISK_PARTITION_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_partition_info)

[IOCTL_DISK_GET_DRIVE_GEOMETRY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_get_drive_geometry)

[IOCTL_DISK_GET_MEDIA_TYPES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_get_media_types)
