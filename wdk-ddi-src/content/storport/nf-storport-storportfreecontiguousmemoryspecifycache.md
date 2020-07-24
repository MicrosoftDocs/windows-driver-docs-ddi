---
UID: NF:storport.StorPortFreeContiguousMemorySpecifyCache
title: StorPortFreeContiguousMemorySpecifyCache function (storport.h)
description: The StorPortFreeContiguousMemorySpecifyCache routine deallocates a range of noncached memory in the nonpaged portion of the system address space.
old-location: storage\storportfreecontiguousmemoryspecifycache.htm
tech.root: storage
ms.assetid: 29735ea8-6125-4958-8d78-12d1f13b16ea
ms.date: 03/29/2018
keywords: ["StorPortFreeContiguousMemorySpecifyCache function"]
ms.keywords: StorPortFreeContiguousMemorySpecifyCache, StorPortFreeContiguousMemorySpecifyCache routine [Storage Devices], storage.storportfreecontiguousmemoryspecifycache, storport/StorPortFreeContiguousMemorySpecifyCache, storprt_4ad11a47-ebb2-4eb9-a7cb-ce0b47d2ab3a.xml
f1_keywords:
 - "storport/StorPortFreeContiguousMemorySpecifyCache"
 - "StorPortFreeContiguousMemorySpecifyCache"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortFreeContiguousMemorySpecifyCache
targetos: Windows
req.typenames: 
---

# StorPortFreeContiguousMemorySpecifyCache function


## -description


The <b>StorPortFreeContiguousMemorySpecifyCache</b> routine deallocates a range of noncached memory in the nonpaged portion of the system address space.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param BaseAddress [in]

The base virtual address to free.


### -param NumberOfBytes [in]

The number of bytes that are allocated to the request. This must be the same number that was supplied as a parameter when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportallocatecontiguousmemoryspecifycachenode">StorPortAllocateContiguousMemorySpecifyCacheNode</a> routine was previously called.


### -param CacheType [in]

The cache type that is used in the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportallocatecontiguousmemoryspecifycachenode">StorPortAllocateContiguousMemorySpecifyCacheNode</a> routine.


## -returns



The <b>StorPortFreeContiguousMemorySpecifyCache</b> routine returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation was successful.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportallocatecontiguousmemoryspecifycachenode">StorPortAllocateContiguousMemorySpecifyCacheNode</a>
 

 

