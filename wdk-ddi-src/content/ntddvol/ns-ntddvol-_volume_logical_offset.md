---
UID: NS:ntddvol._VOLUME_LOGICAL_OFFSET
title: _VOLUME_LOGICAL_OFFSET (ntddvol.h)
description: The VOLUME_LOGICAL_OFFSET structure contains a logical offset into a volume.
old-location: storage\volume_logical_offset.htm
tech.root: storage
ms.assetid: 4b0a982b-63ae-4109-a4be-2dd82824e75a
ms.date: 03/29/2018
ms.keywords: "*PVOLUME_LOGICAL_OFFSET, PVOLUME_LOGICAL_OFFSET, PVOLUME_LOGICAL_OFFSET structure pointer [Storage Devices], VOLUME_LOGICAL_OFFSET, VOLUME_LOGICAL_OFFSET structure [Storage Devices], _VOLUME_LOGICAL_OFFSET, ntddvol/PVOLUME_LOGICAL_OFFSET, ntddvol/VOLUME_LOGICAL_OFFSET, storage.volume_logical_offset, structs-volumemgr_97756e49-7151-4d3a-abbe-aa90a472c284.xml"
f1_keywords:
 - "ntddvol/VOLUME_LOGICAL_OFFSET"
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
- VOLUME_LOGICAL_OFFSET
product:
- Windows
targetos: Windows
req.typenames: VOLUME_LOGICAL_OFFSET, *PVOLUME_LOGICAL_OFFSET
---

# _VOLUME_LOGICAL_OFFSET structure


## -description


The VOLUME_LOGICAL_OFFSET structure contains a logical offset into a volume. 


## -struct-fields




### -field LogicalOffset

Contains a logical offset in bytes into a volume. 


## -remarks



The VOLUME_LOGICAL_OFFSET structure is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_physical_to_logical">IOCTL_VOLUME_PHYSICAL_TO_LOGICAL</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_logical_to_physical">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a> to request a logical offset equivalent of a physical offset or a physical offset equivalent of a logical offset, respectively. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_logical_to_physical">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_physical_to_logical">IOCTL_VOLUME_PHYSICAL_TO_LOGICAL</a>
 

 

