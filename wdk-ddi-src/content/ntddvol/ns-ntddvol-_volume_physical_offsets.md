---
UID: NS:ntddvol._VOLUME_PHYSICAL_OFFSETS
title: "_VOLUME_PHYSICAL_OFFSETS"
author: windows-driver-content
description: The VOLUME_PHYSICAL_OFFSETS structure contains an array of physical offsets and accompanying physical disk numbers and is used with IOCTL_VOLUME_LOGICAL_TO_PHYSICAL to request a series of pairs of physical offsets and disk numbers that correspond to a single logical offset.
old-location: storage\volume_physical_offsets.htm
old-project: storage
ms.assetid: 876cb283-ce0d-44ed-b515-d4ee31089b88
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.volume_physical_offsets, ntddvol/VOLUME_PHYSICAL_OFFSETS, VOLUME_PHYSICAL_OFFSETS structure [Storage Devices], *PVOLUME_PHYSICAL_OFFSETS, _VOLUME_PHYSICAL_OFFSETS, PVOLUME_PHYSICAL_OFFSETS structure pointer [Storage Devices], PVOLUME_PHYSICAL_OFFSETS, VOLUME_PHYSICAL_OFFSETS, ntddvol/PVOLUME_PHYSICAL_OFFSETS, structs-volumemgr_f5ee82b1-a42a-47aa-a3fd-116eeb3b441b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddvol.h
apiname:
-	VOLUME_PHYSICAL_OFFSETS
product: Windows
targetos: Windows
req.typenames: VOLUME_PHYSICAL_OFFSETS, *PVOLUME_PHYSICAL_OFFSETS
---

# _VOLUME_PHYSICAL_OFFSETS structure


## -description


The VOLUME_PHYSICAL_OFFSETS structure contains an array of physical offsets and accompanying physical disk numbers and is used with <a href="..\ntddvol\ni-ntddvol-ioctl_volume_logical_to_physical.md">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a> to request a series of pairs of physical offsets and disk numbers that correspond to a single logical offset. 


## -syntax


````
typedef struct _VOLUME_PHYSICAL_OFFSETS {
  ULONG                  NumberOfPhysicalOffsets;
  VOLUME_PHYSICAL_OFFSET PhysicalOffset[ANYSIZE_ARRAY];
} VOLUME_PHYSICAL_OFFSETS, *PVOLUME_PHYSICAL_OFFSETS;
````


## -struct-fields




### -field NumberOfPhysicalOffsets

Contains the number of physical offsets returned by the call to <a href="..\ntddvol\ni-ntddvol-ioctl_volume_logical_to_physical.md">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a>. 


### -field PhysicalOffset

Contains an array of structures of type <a href="..\ntddvol\ns-ntddvol-_volume_physical_offset.md">VOLUME_PHYSICAL_OFFSET</a>. Each element of the array contains a pair consisting of a physical disk number and an accompanying physical offset &lt;disk number, disk offset&gt;. 


## -see-also

<a href="..\ntddvol\ni-ntddvol-ioctl_volume_logical_to_physical.md">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a>



<a href="..\ntddvol\ns-ntddvol-_volume_physical_offset.md">VOLUME_PHYSICAL_OFFSET</a>



<a href="..\ntddvol\ni-ntddvol-ioctl_volume_physical_to_logical.md">IOCTL_VOLUME_PHYSICAL_TO_LOGICAL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20VOLUME_PHYSICAL_OFFSETS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

