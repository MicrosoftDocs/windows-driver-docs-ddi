---
UID: NS:ks._KSALLOCATOR_DISPATCH
title: _KSALLOCATOR_DISPATCH (ks.h)
description: The KSALLOCATOR_DISPATCH structure contains the callbacks required for a pin to implement its own kernel-level allocator.
old-location: stream\ksallocator_dispatch.htm
tech.root: stream
ms.assetid: 6e6e6dde-3b41-44a7-b51d-1b1f06db0853
ms.date: 04/23/2018
keywords: ["KSALLOCATOR_DISPATCH structure"]
ms.keywords: "*PKSALLOCATOR_DISPATCH, KSALLOCATOR_DISPATCH, KSALLOCATOR_DISPATCH structure [Streaming Media Devices], PKSALLOCATOR_DISPATCH, PKSALLOCATOR_DISPATCH structure pointer [Streaming Media Devices], _KSALLOCATOR_DISPATCH, avstruct_73d2c793-a55a-45f3-af31-fc18240ca1df.xml, ks/KSALLOCATOR_DISPATCH, ks/PKSALLOCATOR_DISPATCH, stream.ksallocator_dispatch"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
req.typenames: KSALLOCATOR_DISPATCH, *PKSALLOCATOR_DISPATCH
f1_keywords:
 - _KSALLOCATOR_DISPATCH
 - ks/_KSALLOCATOR_DISPATCH
 - PKSALLOCATOR_DISPATCH
 - ks/PKSALLOCATOR_DISPATCH
 - KSALLOCATOR_DISPATCH
 - ks/KSALLOCATOR_DISPATCH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSALLOCATOR_DISPATCH
---

# _KSALLOCATOR_DISPATCH structure


## -description

The KSALLOCATOR_DISPATCH structure contains the callbacks required for a pin to implement its own kernel-level allocator.

## -struct-fields

### -field InitializeAllocator

A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkspininitializeallocator">AVStrMiniInitializeAllocator</a> callback routine.

### -field DeleteAllocator

A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnksdeleteallocator">AVStrMiniDeleteAllocator</a> callback routine.

### -field Allocate

A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnksdefaultallocate">AVStrMiniAllocate</a> callback routine.

### -field Free

A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnksdefaultfree">AVStrMiniAllocatorFreeFrame</a> callback routine.

## -remarks

By providing a pointer to a KSALLOCATOR_DISPATCH structure in the relevant <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a> structure, a minidriver declares that the corresponding pin is capable of performing kernel-level allocation. The allocator might or might not be used by the graph manager. Note that memory allocated at kernel level cannot be passed to a user-mode filter.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a>

