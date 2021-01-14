---
UID: NS:ntddvol._VOLUME_PHYSICAL_OFFSET
title: _VOLUME_PHYSICAL_OFFSET (ntddvol.h)
description: The VOLUME_PHYSICAL_OFFSET structure contains a physical offset into a volume and its accompanying physical disk number and is used with IOCTL_VOLUME_PHYSICAL_TO_LOGICAL and IOCTL_VOLUME_LOGICAL_TO_PHYSICAL to request a logical offset equivalent of a physical offset or a physical offset equivalent of a logical offset, respectively.
old-location: storage\volume_physical_offset.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["VOLUME_PHYSICAL_OFFSET structure"]
ms.keywords: "*PVOLUME_PHYSICAL_OFFSET, PVOLUME_PHYSICAL_OFFSET, PVOLUME_PHYSICAL_OFFSET structure pointer [Storage Devices], VOLUME_PHYSICAL_OFFSET, VOLUME_PHYSICAL_OFFSET structure [Storage Devices], _VOLUME_PHYSICAL_OFFSET, ntddvol/PVOLUME_PHYSICAL_OFFSET, ntddvol/VOLUME_PHYSICAL_OFFSET, storage.volume_physical_offset, structs-volumemgr_e42e629d-ed2f-49f3-a669-d2547d46eaa6.xml"
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
targetos: Windows
req.typenames: VOLUME_PHYSICAL_OFFSET, *PVOLUME_PHYSICAL_OFFSET
f1_keywords:
 - _VOLUME_PHYSICAL_OFFSET
 - ntddvol/_VOLUME_PHYSICAL_OFFSET
 - PVOLUME_PHYSICAL_OFFSET
 - ntddvol/PVOLUME_PHYSICAL_OFFSET
 - VOLUME_PHYSICAL_OFFSET
 - ntddvol/VOLUME_PHYSICAL_OFFSET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddvol.h
api_name:
 - _VOLUME_PHYSICAL_OFFSET
 - PVOLUME_PHYSICAL_OFFSET
 - VOLUME_PHYSICAL_OFFSET
---

# _VOLUME_PHYSICAL_OFFSET structure


## -description

The VOLUME_PHYSICAL_OFFSET structure contains a physical offset into a volume and its accompanying physical disk number and is used with <a href="/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_physical_to_logical">IOCTL_VOLUME_PHYSICAL_TO_LOGICAL</a> and <a href="/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_logical_to_physical">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a> to request a logical offset equivalent of a physical offset or a physical offset equivalent of a logical offset, respectively.

## -struct-fields

### -field DiskNumber

Contains the number of the physical disk.

### -field Offset

Contains the physical offset in bytes of the data on the disk.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_logical_to_physical">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a>



<a href="/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_physical_to_logical">IOCTL_VOLUME_PHYSICAL_TO_LOGICAL</a>

