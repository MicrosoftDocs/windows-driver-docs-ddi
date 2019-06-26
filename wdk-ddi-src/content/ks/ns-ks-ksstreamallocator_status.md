---
UID: NS:ks.__unnamed_struct_44
title: KSSTREAMALLOCATOR_STATUS (ks.h)
description: The KSSTREAMALLOCATOR_STATUS structure describes framing requirements and current number of allocated frames for a specific allocator.
old-location: stream\ksstreamallocator_status.htm
tech.root: stream
ms.assetid: 95ef6c1e-c2b7-49ca-9aaf-caeb2dca7c3a
ms.date: 04/23/2018
ms.keywords: "*PKSSTREAMALLOCATOR_STATUS, KSSTREAMALLOCATOR_STATUS, KSSTREAMALLOCATOR_STATUS structure [Streaming Media Devices], PKSSTREAMALLOCATOR_STATUS, PKSSTREAMALLOCATOR_STATUS structure pointer [Streaming Media Devices], ks-struct_e9071d70-ee9c-4ef9-828e-81d9abf6cc68.xml, ks/KSSTREAMALLOCATOR_STATUS, ks/PKSSTREAMALLOCATOR_STATUS, stream.ksstreamallocator_status"
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
- ks.h
api_name:
- KSSTREAMALLOCATOR_STATUS
product:
- Windows
targetos: Windows
req.typenames: KSSTREAMALLOCATOR_STATUS, *PKSSTREAMALLOCATOR_STATUS
---

# KSSTREAMALLOCATOR_STATUS structure


## -description


The KSSTREAMALLOCATOR_STATUS structure describes framing requirements and current number of allocated frames for a specific allocator.


## -struct-fields




### -field Framing

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksallocator_framing">KSALLOCATOR_FRAMING</a> structure that contains the framing specified when the allocator was created.


### -field AllocatedFrames

Contains the current number of allocated frames. This value changes on an extremely frequent basis.


### -field Reserved

Reserved and set to zero.


## -remarks



Clients can query allocator status by providing a KSSTREAMALLOCATOR_STATUS structure in a <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-streamallocator-status">KSPROPERTY_STREAMALLOCATOR_STATUS</a> property request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksallocator_framing">KSALLOCATOR_FRAMING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-streamallocator-status">KSPROPERTY_STREAMALLOCATOR_STATUS</a>
 

 

