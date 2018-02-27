---
UID: NS:irb._IDE_MINIPORT_RESOURCES
title: "_IDE_MINIPORT_RESOURCES"
author: windows-driver-content
description: The IDE_MINIPORT_RESOURCES structure is used by the port driver to provide the miniport driver with resources.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_miniport_resources.htm
old-project: storage
ms.assetid: 867b6152-9846-484f-9eac-07d0f24d55df
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PIDE_MINIPORT_RESOURCES, IDE_MINIPORT_RESOURCES, IDE_MINIPORT_RESOURCES structure [Storage Devices], PIDE_MINIPORT_RESOURCES, PIDE_MINIPORT_RESOURCES structure pointer [Storage Devices], _IDE_MINIPORT_RESOURCES, irb/IDE_MINIPORT_RESOURCES, irb/PIDE_MINIPORT_RESOURCES, storage.ide_miniport_resources, structs-ATA_28df7197-d4b0-4279-a4db-e9b1269f6ba7.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: irb.h
req.include-header: Irb.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	irb.h
api_name:
-	IDE_MINIPORT_RESOURCES
product: Windows
targetos: Windows
req.typenames: IDE_MINIPORT_RESOURCES, *PIDE_MINIPORT_RESOURCES
---

# _IDE_MINIPORT_RESOURCES structure


## -description


The IDE_MINIPORT_RESOURCES structure is used by the port driver to provide the miniport driver with resources.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _IDE_MINIPORT_RESOURCES {
  ULONG             NumberOfAccessRanges;
  PIDE_ACCESS_RANGE IdeAccessRange;
} IDE_MINIPORT_RESOURCES, *PIDE_MINIPORT_RESOURCES;
````


## -struct-fields




### -field NumberOfAccessRanges

Contains the number of access ranges pointed to by <b>IdeAccessRange</b>. Each is a range either of memory addresses or I/O port addresses.


### -field IdeAccessRange

Pointer to the first address range in a series of contiguous address ranges defined by a structure of type <a href="..\irb\ns-irb-_ide_access_range.md">IDE_ACCESS_RANGE</a>. The value in the <b>NumberOfAccessRanges</b> member indicates how many address ranges are provided. The port driver populates each <b>IDE_ACCESS_RANGE</b> structure with the address ranges allocated for the controller.


## -remarks



The port driver passes this structure to the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a> routine.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a>



<a href="..\irb\ns-irb-_ide_access_range.md">IDE_ACCESS_RANGE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IDE_MINIPORT_RESOURCES structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

