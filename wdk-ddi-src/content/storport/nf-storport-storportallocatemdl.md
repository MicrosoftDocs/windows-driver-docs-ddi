---
UID: NF:storport.StorPortAllocateMdl
title: StorPortAllocateMdl function
author: windows-driver-content
description: The StorPortAllocateMdl routine allocates an MDL to describe the given non-paged pool memory.
old-location: storage\storportallocatemdl.htm
old-project: storage
ms.assetid: 45450486-3264-4fc8-8051-f7c48997e3dd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortAllocateMdl, StorPortAllocateMdl routine [Storage Devices], storage.storportallocatemdl, storport/StorPortAllocateMdl, storprt_d80c510f-4cc4-4687-ab5b-9b9b5cf399ce.xml
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
-	StorPortAllocateMdl
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortAllocateMdl function


## -description


The <b>StorPortAllocateMdl</b> routine allocates an MDL to describe the given non-paged pool memory.


## -syntax


````
ULONG StorPortAllocateMdl(
  _In_  PVOID HwDeviceExtension,
  _In_  PVOID BufferPointer,
  _In_  ULONG NumberOfBytes,
  _Out_ PVOID *Mdl
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param BufferPointer [in]

A pointer to the base virtual address of the buffer that the MDL is to describe.


### -param NumberOfBytes [in]

This parameter specifies the length, in bytes, of the buffer that the MDL is to describe.


### -param Mdl [out]

A pointer to receive the allocated MDL.


## -returns



StorPortAllocateMdl returns one of the following status codes:

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
Indicates that the routine allocated the MDL successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The pointer to receive the MDL is <b>NULL</b>.

The pointer to the buffer is <b>NULL</b>.

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
Unable to allocate MDL to describe the given buffer.

</td>
</tr>
</table>
 




## -remarks



A miniport driver calls the <b>StorPortAllocateMdl</b> routine to allocate an MDL to describe a block of memory from the non-paged pool. To free the MDL, the miniport driver calls the <a href="..\storport\nf-storport-storportfreepool.md">StorPortFreeMdl</a> routine.



