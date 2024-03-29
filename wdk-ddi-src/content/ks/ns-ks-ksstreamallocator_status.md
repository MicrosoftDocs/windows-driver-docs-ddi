---
UID: NS:ks.KSSTREAMALLOCATOR_STATUS
title: KSSTREAMALLOCATOR_STATUS (ks.h)
description: The KSSTREAMALLOCATOR_STATUS structure describes framing requirements and current number of allocated frames for a specific allocator.
old-location: stream\ksstreamallocator_status.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSSTREAMALLOCATOR_STATUS structure"]
ms.keywords: "*PKSSTREAMALLOCATOR_STATUS, KSSTREAMALLOCATOR_STATUS, KSSTREAMALLOCATOR_STATUS structure [Streaming Media Devices], PKSSTREAMALLOCATOR_STATUS, PKSSTREAMALLOCATOR_STATUS structure pointer [Streaming Media Devices], ks-struct_e9071d70-ee9c-4ef9-828e-81d9abf6cc68.xml, ks/KSSTREAMALLOCATOR_STATUS, ks/PKSSTREAMALLOCATOR_STATUS, stream.ksstreamallocator_status"
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
targetos: Windows
req.typenames: KSSTREAMALLOCATOR_STATUS, *PKSSTREAMALLOCATOR_STATUS
f1_keywords:
 - PKSSTREAMALLOCATOR_STATUS
 - ks/PKSSTREAMALLOCATOR_STATUS
 - KSSTREAMALLOCATOR_STATUS
 - ks/KSSTREAMALLOCATOR_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKSSTREAMALLOCATOR_STATUS
 - KSSTREAMALLOCATOR_STATUS
---

# KSSTREAMALLOCATOR_STATUS structure


## -description

The KSSTREAMALLOCATOR_STATUS structure describes framing requirements and current number of allocated frames for a specific allocator.

## -struct-fields

### -field Framing

A <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing">KSALLOCATOR_FRAMING</a> structure that contains the framing specified when the allocator was created.

### -field AllocatedFrames

Contains the current number of allocated frames. This value changes on an extremely frequent basis.

### -field Reserved

Reserved and set to zero.

## -remarks

Clients can query allocator status by providing a KSSTREAMALLOCATOR_STATUS structure in a <a href="/windows-hardware/drivers/stream/ksproperty-streamallocator-status">KSPROPERTY_STREAMALLOCATOR_STATUS</a> property request.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing">KSALLOCATOR_FRAMING</a>



<a href="/windows-hardware/drivers/stream/ksproperty-streamallocator-status">KSPROPERTY_STREAMALLOCATOR_STATUS</a>

