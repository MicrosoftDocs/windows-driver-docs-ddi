---
UID: NS:ntddvol._VOLUME_LOGICAL_OFFSET
title: "_VOLUME_LOGICAL_OFFSET"
author: windows-driver-content
description: The VOLUME_LOGICAL_OFFSET structure contains a logical offset into a volume.
old-location: storage\volume_logical_offset.htm
old-project: storage
ms.assetid: 4b0a982b-63ae-4109-a4be-2dd82824e75a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: VOLUME_LOGICAL_OFFSET, structs-volumemgr_97756e49-7151-4d3a-abbe-aa90a472c284.xml, storage.volume_logical_offset, PVOLUME_LOGICAL_OFFSET, _VOLUME_LOGICAL_OFFSET, ntddvol/PVOLUME_LOGICAL_OFFSET, VOLUME_LOGICAL_OFFSET structure [Storage Devices], *PVOLUME_LOGICAL_OFFSET, ntddvol/VOLUME_LOGICAL_OFFSET, PVOLUME_LOGICAL_OFFSET structure pointer [Storage Devices]
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
-	VOLUME_LOGICAL_OFFSET
product: Windows
targetos: Windows
req.typenames: "*PVOLUME_LOGICAL_OFFSET, VOLUME_LOGICAL_OFFSET"
---

# _VOLUME_LOGICAL_OFFSET structure


## -description


The VOLUME_LOGICAL_OFFSET structure contains a logical offset into a volume. 


## -syntax


````
typedef struct _VOLUME_LOGICAL_OFFSET {
  LONGLONG LogicalOffset;
} VOLUME_LOGICAL_OFFSET, *PVOLUME_LOGICAL_OFFSET;
````


## -struct-fields




### -field LogicalOffset

Contains a logical offset in bytes into a volume. 


## -remarks



The VOLUME_LOGICAL_OFFSET structure is used with <a href="..\ntddvol\ni-ntddvol-ioctl_volume_physical_to_logical.md">IOCTL_VOLUME_PHYSICAL_TO_LOGICAL</a> and <a href="..\ntddvol\ni-ntddvol-ioctl_volume_logical_to_physical.md">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a> to request a logical offset equivalent of a physical offset or a physical offset equivalent of a logical offset, respectively. 




## -see-also

<a href="..\ntddvol\ni-ntddvol-ioctl_volume_logical_to_physical.md">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a>



<a href="..\ntddvol\ni-ntddvol-ioctl_volume_physical_to_logical.md">IOCTL_VOLUME_PHYSICAL_TO_LOGICAL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20VOLUME_LOGICAL_OFFSET structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

