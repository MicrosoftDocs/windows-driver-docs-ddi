---
UID: NF:storport.StorPortAllocateContiguousMemorySpecifyCacheNode
title: StorPortAllocateContiguousMemorySpecifyCacheNode function (storport.h)
description: The StorPortAllocateContiguousMemorySpecifyCacheNode routine allocates a range of physically contiguous noncached, nonpaged memory.
old-location: storage\storportallocatecontiguousmemoryspecifycachenode.htm
tech.root: storage
ms.assetid: b2ed8c88-9ffd-4601-8fd0-c9390e9ba84d
ms.date: 03/29/2018
ms.keywords: StorPortAllocateContiguousMemorySpecifyCacheNode, StorPortAllocateContiguousMemorySpecifyCacheNode routine [Storage Devices], storage.storportallocatecontiguousmemoryspecifycachenode, storport/StorPortAllocateContiguousMemorySpecifyCacheNode, storprt_d91d6ab4-677e-4bc0-a0b5-1c252475ecbb.xml
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortAllocateContiguousMemorySpecifyCacheNode
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortAllocateContiguousMemorySpecifyCacheNode function


## -description


The <b>StorPortAllocateContiguousMemorySpecifyCacheNode</b> routine allocates a range of physically contiguous noncached, nonpaged memory.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param NumberOfBytes [in]

The number of bytes to allocate.


### -param LowestAcceptableAddress [in]

The lowest physical address that is valid for the allocation. For example, if the device can only reference physical memory in the 8 MB to 16 MB range, this value would be set to 0x800000 (8 MB).


### -param HighestAcceptableAddress [in]

The highest physical address that is valid for the allocation. For example, if the device can only reference physical memory below 16 MB, this value would be set to 0xFFFFFF (16 MB - 1).


### -param BoundaryAddressMultiple [in, optional]

The physical address multiple that this allocation must not cross.


### -param CacheType [in]

The desired cache type for the mapping.


### -param PreferredNode [in]

The preferred node from which the allocation should be made if pages are available on that node.


### -param BufferPointer [out]

The variable that receives the starting address of the allocated memory block. Upon return from this routine, if this variable is zero, a contiguous range could not be found to satisfy the request. If this variable is not <b>NULL</b>, it contains a pointer (for example, a virtual address in the nonpaged portion of the system) to the allocated physically contiguous memory.


## -returns



The <b>StorPortAllocateContiguousMemorySpecifyCacheNode</b> routine returns one of the following status codes:

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
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The operation failed to allocate the requested memory because of insufficient resources.

</td>
</tr>
</table>
 




## -remarks



If the request fails, <i>BufferPointer</i> will be set to <b>NULL</b>.



