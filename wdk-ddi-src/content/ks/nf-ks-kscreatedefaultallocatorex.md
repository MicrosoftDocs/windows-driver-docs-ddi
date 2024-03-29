---
UID: NF:ks.KsCreateDefaultAllocatorEx
title: KsCreateDefaultAllocatorEx function (ks.h)
description: Creates a default allocator that uses the specified memory pool and associates the IoGetCurrentIrpStackLocation(pIrp)-&gt;FileObject with this allocator using an internal dispatch table (KSDISPATCH_TABLE).
old-location: stream\kscreatedefaultallocatorex.htm
tech.root: stream
ms.date: 06/25/2020
keywords: ["KsCreateDefaultAllocatorEx function"]
ms.keywords: KsCreateDefaultAllocatorEx, KsCreateDefaultAllocatorEx function [Streaming Media Devices], ks/KsCreateDefaultAllocatorEx, ksfunc_99b91933-c8d3-4580-bd51-a6620defcf30.xml, stream.kscreatedefaultallocatorex
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsCreateDefaultAllocatorEx
 - ks/KsCreateDefaultAllocatorEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsCreateDefaultAllocatorEx
---

# KsCreateDefaultAllocatorEx function


## -description

Creates a default allocator that uses the specified memory pool and associates the *IoGetCurrentIrpStackLocation(pIrp)->FileObject* with this allocator using an internal dispatch table (KSDISPATCH_TABLE).

## -parameters

### -param Irp [in]


Contains the IRP with the allocator create request being handled.

### -param InitializeContext [in, optional]


Optionally contains a context to use with an external allocator. This is only used as the initialization context to the optional InitializeAllocator callback when creating an allocator context. The parameter is not otherwise used. If an external allocator is not provided, this parameter must be set to **NULL**.

### -param DefaultAllocate [in, optional]


Optionally contains an external allocate function that is used in place of the default pool allocation. If this is **NULL**, default allocation is used.

### -param DefaultFree [in, optional]


Optionally contains an external free function that is used in place of the default pool allocation. If an external allocator is not provided, this parameter must be set to **NULL**.

### -param InitializeAllocator [in, optional]


Optionally contains an external allocator initialization function to which the InitializeContext parameter is passed. This function is expected to return an allocator context based on the allocator framing. If an external allocator is not provided, this parameter must be set to **NULL**.

### -param DeleteAllocator [in, optional]


Optionally contains an external allocator delete function that is used for external allocators.  If an external allocator is not provided, this parameter must be set to **NULL**.

## -returns

Returns STATUS_SUCCESS, else an error on default allocator creation failure. Does not complete the IRP or set the status in the IRP.

## -remarks

Before calling this routine, the **KSCREATE_ITEM_IRP_STORAGE(Irp)** macro should return a pointer to the [KSOBJECT_CREATE_ITEM](./ns-ks-ksobject_create_item.md) structure that is the create item for this allocator. **KsCreateDefaultAllocatorEx** sets **FsContext** to point to the return value of this macro. As such, **FsContext** can later be used for security descriptor queries or changes.

You can find **KSCREATE_ITEM_IRP_STORAGE(Irp)** and related macros in *ks.h*.
