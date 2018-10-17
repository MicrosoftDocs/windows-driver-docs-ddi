---
UID: NF:storport.StorPortFreePool
title: StorPortFreePool function
author: windows-driver-content
description: The StorPortFreePool routine frees a block of memory that was previously allocated by a call to the StorPortAllocatePool routine.
old-location: storage\storportfreepool.htm
tech.root: storage
ms.assetid: e5886fa3-dc37-4764-9304-3609a4ced0ad
ms.date: 3/29/2018
ms.keywords: StorPortFreePool, StorPortFreePool routine [Storage Devices], storage.storportfreepool, storport/StorPortFreePool, storprt_a4fd5e23-3c56-4bf3-9751-21f90028d704.xml
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
-	StorPortFreePool
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortFreePool function


## -description


The <b>StorPortFreePool</b> routine frees a block of memory that was previously allocated by a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567031">StorPortAllocatePool</a> routine.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param BufferPointer [in]

A pointer to the block of memory to free. This must be a pointer that was returned by a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567031">StorPortAllocatePool</a> routine.


## -returns



StorPortFreePool returns one of the following status codes:

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
Indicates that the routine freed the memory block successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The pointer to the memory block to be freed is <b>NULL</b>.

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
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567031">StorPortAllocatePool</a>
 

 

