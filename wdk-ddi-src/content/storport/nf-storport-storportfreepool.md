---
UID: NF:storport.StorPortFreePool
title: StorPortFreePool function
author: windows-driver-content
description: The StorPortFreePool routine frees a block of memory that was previously allocated by a call to the StorPortAllocatePool routine.
old-location: storage\storportfreepool.htm
old-project: storage
ms.assetid: e5886fa3-dc37-4764-9304-3609a4ced0ad
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.storportfreepool, storprt_a4fd5e23-3c56-4bf3-9751-21f90028d704.xml, storport/StorPortFreePool, StorPortFreePool routine [Storage Devices], StorPortFreePool
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
-	StorPortFreePool
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortFreePool function


## -description


The <b>StorPortFreePool</b> routine frees a block of memory that was previously allocated by a call to the <a href="..\storport\nf-storport-storportallocatepool.md">StorPortAllocatePool</a> routine.


## -syntax


````
ULONG StorPortFreePool(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID BufferPointer
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param BufferPointer [in]

A pointer to the block of memory to free. This must be a pointer that was returned by a previous call to the <a href="..\storport\nf-storport-storportallocatepool.md">StorPortAllocatePool</a> routine.


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

<a href="..\storport\nf-storport-storportallocatepool.md">StorPortAllocatePool</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortFreePool routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

