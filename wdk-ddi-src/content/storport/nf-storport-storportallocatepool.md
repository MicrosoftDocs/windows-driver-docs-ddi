---
UID: NF:storport.StorPortAllocatePool
title: StorPortAllocatePool function
author: windows-driver-content
description: The StorPortAllocatePool routine allocates a block of non-contiguous, non-paged pool memory.
old-location: storage\storportallocatepool.htm
old-project: storage
ms.assetid: e6823b9c-9717-49ab-8e67-c1d522774826
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storport/StorPortAllocatePool, storage.storportallocatepool, StorPortAllocatePool routine [Storage Devices], storprt_4ede181d-6ccf-47af-974d-b0daaa6e723a.xml, StorPortAllocatePool
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortAllocatePool2, StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	StorPortAllocatePool
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortAllocatePool function


## -description


The <b>StorPortAllocatePool</b> routine allocates a block of non-contiguous, non-paged pool memory.


## -syntax


````
ULONG StorPortAllocatePool(
  _In_  PVOID HwDeviceExtension,
  _In_  ULONG NumberOfBytes,
  _In_  ULONG Tag,
  _Out_ PVOID *BufferPointer
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param NumberOfBytes [in]

The size, in bytes, of the block of memory being allocated.


### -param Tag [in]

The pool tag for the allocated memory. Drivers specify the pool tag as a string of four characters, delimited by single quotation marks. The string is usually specified in reverse order. The ASCII value of each character in the tag must be between zero and 127.


### -param BufferPointer [out]

A pointer to the address of the allocated memory block or <b>NULL</b> if not successful. 


## -returns


StorPortAllocatePool returns one of the following status codes:
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
Indicates that the routine successfully allocated a memory block of the requested size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The pointer to receive the buffer address is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
The call was made at an invalid IRQL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Unable to allocate memory of the requested size.

</td>
</tr>
</table> 



## -remarks


A miniport driver calls the <b>StorPortAllocatePool</b> routine to allocate a block of non-contiguous memory from the non-paged pool. To free the block of memory, the miniport driver calls the <a href="..\storport\nf-storport-storportfreepool.md">StorPortFreePool</a> routine. If the request fails, BufferPointer will be set to <b>NULL</b>.


