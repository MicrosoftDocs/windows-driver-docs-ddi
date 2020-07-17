---
UID: NS:ntddvol._VOLUME_DISK_EXTENTS
title: _VOLUME_DISK_EXTENTS (ntddvol.h)
description: The VOLUME_DISK_EXTENTS structure is used in conjunction with the IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS request to retrieve information about all the extents on a given volume.
old-location: storage\volume_disk_extents.htm
tech.root: storage
ms.assetid: 227846c2-8794-4859-89af-c139ead32143
ms.date: 03/29/2018
keywords: ["_VOLUME_DISK_EXTENTS structure"]
ms.keywords: "*PVOLUME_DISK_EXTENTS, PVOLUME_DISK_EXTENTS, PVOLUME_DISK_EXTENTS structure pointer [Storage Devices], VOLUME_DISK_EXTENTS, VOLUME_DISK_EXTENTS structure [Storage Devices], _VOLUME_DISK_EXTENTS, ntddvol/PVOLUME_DISK_EXTENTS, ntddvol/VOLUME_DISK_EXTENTS, storage.volume_disk_extents, structs-volumemgr_148847d4-324c-4767-8247-7d286e496d42.xml"
f1_keywords:
 - "ntddvol/VOLUME_DISK_EXTENTS"
 - "VOLUME_DISK_EXTENTS"
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
- VOLUME_DISK_EXTENTS
product:
- Windows
targetos: Windows
req.typenames: VOLUME_DISK_EXTENTS, *PVOLUME_DISK_EXTENTS
---

# _VOLUME_DISK_EXTENTS structure


## -description


The VOLUME_DISK_EXTENTS structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_get_volume_disk_extents">IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS</a> request to retrieve information about all the extents on a given volume.


## -struct-fields




### -field NumberOfDiskExtents

Indicates the number of extents that comprise the volume, which can span multiple disks. 


### -field Extents

Indicates the number of extents that comprise the volume, which can span multiple disks. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ns-ntddvol-_disk_extent">DISK_EXTENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_get_volume_disk_extents">IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS</a>



disk extent
 

 

