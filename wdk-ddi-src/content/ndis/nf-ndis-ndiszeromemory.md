---
UID: NF:ndis.NdisZeroMemory
title: NdisZeroMemory macro
author: windows-driver-content
description: The NdisZeroMemory function fills a block of memory with zeros.
old-location: netvista\ndiszeromemory.htm
old-project: netvista
ms.assetid: 1cb829e1-bd4f-4d6b-a936-0e7cf8024381
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisZeroMemory, NdisZeroMemory macro [Network Drivers Starting with Windows Vista], ndis/NdisZeroMemory, ndis_memory_ref_06fa3e0b-cb08-41c7-8e09-debec8e323c0.xml, netvista.ndiszeromemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlZeroMemory instead.
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisZeroMemory
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisZeroMemory macro


## -description


The 
  <b>NdisZeroMemory</b> function fills a block of memory with zeros.


## -parameters




### -param Destination [in]

The base virtual address of a block of memory.


### -param Length [in]

The number of bytes to fill with zeros.


## -remarks



<b>NdisZeroMemory</b> fills the specified range of memory with zeros. The given 
    <i>Destination</i> and 
    <i>Length</i> must be a proper subrange of a caller-accessible memory range.

As long as the given range was allocated from nonpaged pool, the caller can be running at any IRQL.
    Otherwise, a caller must be running at IRQL &lt; DISPATCH_LEVEL as, for example, when a caller clears a
    structure it allocated on the stack.




## -see-also




<a href="https://msdn.microsoft.com/aac4049c-a876-4bbb-ba3b-fa36c299e1c7">
   NdisAllocateMemoryWithTagPriority</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564692">NdisZeroMappedMemory</a>
 

 

