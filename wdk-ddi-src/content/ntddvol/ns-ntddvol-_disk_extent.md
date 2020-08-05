---
UID: NS:ntddvol._DISK_EXTENT
title: _DISK_EXTENT (ntddvol.h)
description: The DISK_EXTENT structure contains information defining the location and length of a volume extent on a disk.
old-location: storage\disk_extent.htm
tech.root: storage
ms.assetid: 74ffdfba-1b80-479d-9637-43222a438fa9
ms.date: 03/29/2018
keywords: ["DISK_EXTENT structure"]
ms.keywords: "*PDISK_EXTENT, DISK_EXTENT, DISK_EXTENT structure [Storage Devices], PDISK_EXTENT, PDISK_EXTENT structure pointer [Storage Devices], _DISK_EXTENT, ntddvol/DISK_EXTENT, ntddvol/PDISK_EXTENT, storage.disk_extent, structs-disk_2874d2a7-dc4e-46e6-9d43-2374e82c857b.xml"
f1_keywords:
 - "ntddvol/DISK_EXTENT"
 - "DISK_EXTENT"
req.header: ntddvol.h
req.include-header: Ntddvol.h
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
- ntddvol.h
api_name:
- DISK_EXTENT
targetos: Windows
req.typenames: DISK_EXTENT, *PDISK_EXTENT
---

# _DISK_EXTENT structure


## -description


The DISK_EXTENT structure contains information defining the location and length of a volume extent on a disk.


## -struct-fields




### -field DiskNumber

Specifies the number of the disk that contains this extent. This is the same disk number that is used to construct the name of the disk (for example, <i>PhysicalDriveX</i> or <i>HarddiskX</i>, where X is the disk number).


### -field StartingOffset

Specifies the offset, in bytes, from the beginning of the disk.


### -field ExtentLength

Specifies the number of bytes of this extent.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_get_volume_disk_extents">IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ns-ntddvol-_volume_disk_extents">VOLUME_DISK_EXTENTS</a>
 

 

