---
UID: NS:ntdddisk._DISK_GEOMETRY_EX
title: _DISK_GEOMETRY_EX (ntdddisk.h)
description: The DISK_GEOMETRY_EX structure is an arbitrary-length structure composed of a DISK_GEOMETRY structure followed by a DISK_PARTITION_INFO structure followed, in turn, by a DISK_DETECTION_INFO structure.
old-location: storage\disk_geometry_ex.htm
tech.root: storage
ms.date: 01/06/2020
keywords: ["DISK_GEOMETRY_EX structure"]
ms.keywords: "*PDISK_GEOMETRY_EX, DISK_GEOMETRY_EX, DISK_GEOMETRY_EX structure [Storage Devices], PDISK_GEOMETRY_EX, PDISK_GEOMETRY_EX structure pointer [Storage Devices], _DISK_GEOMETRY_EX, ntdddisk/DISK_GEOMETRY_EX, ntdddisk/PDISK_GEOMETRY_EX, storage.disk_geometry_ex, structs-disk_58b543a6-c9ee-4acf-9012-6572e9e9e627.xml"
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
targetos: Windows
req.typenames: DISK_GEOMETRY_EX, *PDISK_GEOMETRY_EX
f1_keywords:
 - _DISK_GEOMETRY_EX
 - ntdddisk/_DISK_GEOMETRY_EX
 - PDISK_GEOMETRY_EX
 - ntdddisk/PDISK_GEOMETRY_EX
 - DISK_GEOMETRY_EX
 - ntdddisk/DISK_GEOMETRY_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - _DISK_GEOMETRY_EX
 - PDISK_GEOMETRY_EX
 - DISK_GEOMETRY_EX
---

# _DISK_GEOMETRY_EX structure


## -description

The DISK_GEOMETRY_EX structure is an arbitrary-length structure composed of a [DISK_GEOMETRY](./ns-ntdddisk-_disk_geometry.md) structure followed by a [DISK_PARTITION_INFO](./ns-ntdddisk-_disk_partition_info.md) structure followed, in turn, by a [DISK_DETECTION_INFO](./ns-ntdddisk-_disk_detection_info.md) structure.

## -struct-fields

### -field Geometry

See [DISK_GEOMETRY](./ns-ntdddisk-_disk_geometry.md) for a description of this member.

### -field DiskSize

Contains the size in bytes of the disk.

### -field Data

Beginning of the data block, starting with a [DISK_PARTITION_INFO](./ns-ntdddisk-_disk_partition_info.md) structure followed by a [DISK_DETECTION_INFO](./ns-ntdddisk-_disk_detection_info.md) structure.

## -remarks

DISK_GEOMETRY_EX is used in conjunction with the [IOCTL_DISK_GET_DRIVE_GEOMETRY_EX](./ni-ntdddisk-ioctl_disk_get_drive_geometry_ex.md) and the [IOCTL_DISK_GET_MEDIA_TYPES](./ni-ntdddisk-ioctl_disk_get_media_types.md) IOCTLs, in order to retrieve information about the geometry of a physical disk (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).

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

[DISK_DETECTION_INFO](./ns-ntdddisk-_disk_detection_info.md)

[DISK_GEOMETRY](./ns-ntdddisk-_disk_geometry.md)

[DISK_PARTITION_INFO](./ns-ntdddisk-_disk_partition_info.md)

[IOCTL_DISK_GET_DRIVE_GEOMETRY](./ni-ntdddisk-ioctl_disk_get_drive_geometry.md)

[IOCTL_DISK_GET_MEDIA_TYPES](./ni-ntdddisk-ioctl_disk_get_media_types.md)

