---
UID: NF:ndis.NdisZeroMemory
title: NdisZeroMemory macro
author: windows-driver-content
description: The NdisZeroMemory function fills a block of memory with zeros.
old-location: netvista\ndiszeromemory.htm
old-project: netvista
ms.assetid: 1cb829e1-bd4f-4d6b-a936-0e7cf8024381
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisZeroMemory macro [Network Drivers Starting with Windows Vista], ndis/NdisZeroMemory, ndis_memory_ref_06fa3e0b-cb08-41c7-8e09-debec8e323c0.xml, NdisZeroMemory, netvista.ndiszeromemory
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
req.lib: ndis.h
req.dll: 
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NdisZeroMemory
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisZeroMemory macro


## -description


The 
  <b>NdisZeroMemory</b> function fills a block of memory with zeros.


## -syntax


````
VOID NdisZeroMemory(
  [in] PVOID Destination,
  [in] ULONG Length
);
````


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

<a href="..\ndis\nf-ndis-ndiszeromappedmemory.md">NdisZeroMappedMemory</a>

<a href="..\ndis\nf-ndis-ndisallocatememorywithtagpriority.md">
   NdisAllocateMemoryWithTagPriority</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisZeroMemory macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

