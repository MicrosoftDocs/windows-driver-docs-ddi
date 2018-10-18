---
UID: NF:ks.KsCreateDefaultAllocatorEx
title: KsCreateDefaultAllocatorEx function
author: windows-driver-content
description: Creates a default allocator that uses the specified memory pool and associates the IoGetCurrentIrpStackLocation(pIrp)-&gt;FileObject with this allocator using an internal dispatch table (KSDISPATCH_TABLE).
old-location: stream\kscreatedefaultallocatorex.htm
tech.root: stream
ms.assetid: 63b2d9a3-7f8e-4c03-8c0c-a4555c27e39c
ms.date: 4/23/2018
ms.keywords: KsCreateDefaultAllocatorEx, KsCreateDefaultAllocatorEx function [Streaming Media Devices], ks/KsCreateDefaultAllocatorEx, ksfunc_99b91933-c8d3-4580-bd51-a6620defcf30.xml, stream.kscreatedefaultallocatorex
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsCreateDefaultAllocatorEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsCreateDefaultAllocatorEx function


## -description


Creates a default allocator that uses the specified memory pool and associates the <i>IoGetCurrentIrpStackLocation(pIrp)-&gt;FileObject</i> with this allocator using an internal dispatch table (KSDISPATCH_TABLE).


## -parameters




### -param Irp [in]

Contains the IRP with the allocator create request being handled.


### -param InitializeContext [in, optional]

Optionally contains a context to use with an external allocator. This is only used as the initialization context to the optional InitializeAllocator callback when creating an allocator context. The parameter is not otherwise used. If an external allocator is not provided, this parameter must be set to <b>NULL</b>.


### -param DefaultAllocate [in, optional]

Optionally contains an external allocate function that is used in place of the default pool allocation. If this is <b>NULL</b>, default allocation is used.


### -param DefaultFree [in, optional]

Optionally contains an external free function that is used in place of the default pool allocation. If an external allocator is not provided, this parameter must be set to <b>NULL</b>.


### -param InitializeAllocator [in, optional]

Optionally contains an external allocator initialization function to which the InitializeContext parameter is passed. This function is expected to return an allocator context based on the allocator framing. If an external allocator is not provided, this parameter must be set to <b>NULL</b>.


### -param DeleteAllocator [in, optional]

Optionally contains an external allocator delete function that is used for external allocators.  If an external allocator is not provided, this parameter must be set to <b>NULL</b>.


## -returns



Returns STATUS_SUCCESS, else an error on default allocator creation failure. Does not complete the IRP or set the status in the IRP.




## -remarks



Before calling this routine, the <b>KSCREATE_ITEM_IRP_STORAGE(Irp)</b> macro should return a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563479">KSOBJECT_CREATE_ITEM</a> structure that is the create item for this allocator. <b>KsCreateDefaultAllocatorEx</b> sets <b>FsContext</b> to point to the return value of this macro. As such, <b>FsContext</b> can later be used for security descriptor queries or changes.

You can find <b>KSCREATE_ITEM_IRP_STORAGE(Irp)</b> and related macros in <i>ks.h</i>.



