---
UID: NF:storport.StorPortFreeContiguousMemorySpecifyCache
title: StorPortFreeContiguousMemorySpecifyCache function
author: windows-driver-content
description: The StorPortFreeContiguousMemorySpecifyCache routine deallocates a range of noncached memory in the nonpaged portion of the system address space.
old-location: storage\storportfreecontiguousmemoryspecifycache.htm
old-project: storage
ms.assetid: 29735ea8-6125-4958-8d78-12d1f13b16ea
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storprt_4ad11a47-ebb2-4eb9-a7cb-ce0b47d2ab3a.xml, StorPortFreeContiguousMemorySpecifyCache, StorPortFreeContiguousMemorySpecifyCache routine [Storage Devices], storage.storportfreecontiguousmemoryspecifycache, storport/StorPortFreeContiguousMemorySpecifyCache
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	StorPortFreeContiguousMemorySpecifyCache
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortFreeContiguousMemorySpecifyCache function


## -description


The <b>StorPortFreeContiguousMemorySpecifyCache</b> routine deallocates a range of noncached memory in the nonpaged portion of the system address space.


## -syntax


````
ULONG StorPortFreeContiguousMemorySpecifyCache(
  _In_ PVOID               HwDeviceExtension,
  _In_ PVOID               BaseAddress,
  _In_ SIZE_T              NumberOfBytes,
  _In_ MEMORY_CACHING_TYPE CacheType
);
````


## -parameters




#### - HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


#### - BaseAddress [in]

The base virtual address to free.


#### - NumberOfBytes [in]

The number of bytes that are allocated to the request. This must be the same number that was supplied as a parameter when the <a href="..\storport\nf-storport-storportallocatecontiguousmemoryspecifycachenode.md">StorPortAllocateContiguousMemorySpecifyCacheNode</a> routine was previously called.


#### - CacheType [in]

The cache type that is used in the call to the <a href="..\storport\nf-storport-storportallocatecontiguousmemoryspecifycachenode.md">StorPortAllocateContiguousMemorySpecifyCacheNode</a> routine.


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

<a href="..\storport\nf-storport-storportallocatecontiguousmemoryspecifycachenode.md">StorPortAllocateContiguousMemorySpecifyCacheNode</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortFreeContiguousMemorySpecifyCache routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

