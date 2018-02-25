---
UID: NF:ntddk.MmFreeContiguousMemorySpecifyCache
title: MmFreeContiguousMemorySpecifyCache function
author: windows-driver-content
description: The MmFreeContiguousMemorySpecifyCache routine frees a buffer that was allocated by an MmAllocateContiguousMemorySpecifyCacheXxx routine.
old-location: kernel\mmfreecontiguousmemoryspecifycache.htm
old-project: kernel
ms.assetid: e5958dd7-b287-4f0d-8677-75d850885262
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, F, M, MmFreeContiguousMemorySpecifyCache, MmFreeContiguousMemorySpecifyCache routine [Kernel-Mode Driver Architecture], S, a, c, e, f, g, h, i, k106_256e3525-d48d-4045-872c-2e2fd6302525.xml, kernel.mmfreecontiguousmemoryspecifycache, m, n, o, p, r, s, t, u, wdm/MmFreeContiguousMemorySpecifyCache, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmFreeContiguousMemorySpecifyCache
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# MmFreeContiguousMemorySpecifyCache function


## -description


The <b>MmFreeContiguousMemorySpecifyCache</b> routine frees a buffer that was allocated by an <b>MmAllocateContiguousMemorySpecifyCache<i>Xxx</i></b> routine. 


## -syntax


````
VOID MmFreeContiguousMemorySpecifyCache(
  _In_ PVOID               BaseAddress,
  _In_ SIZE_T              NumberOfBytes,
  _In_ MEMORY_CACHING_TYPE CacheType
);
````


## -parameters




### -param BaseAddress [in]

Specifies the base address of the buffer to be freed. Must match the address returned by the <b>MmAllocateContiguousMemorySpecifyCache<i>Xxx</i></b> call that allocated the buffer.


### -param NumberOfBytes [in]

Specifies the size in bytes of the buffer to be freed. Must match the size requested when the buffer was allocated by the <b>MmAllocateContiguousMemorySpecifyCache<i>Xxx</i></b> routine.


### -param CacheType [in]

Specifies the cache type of the buffer to be freed. Must match the cache type requested when the buffer was allocated by the <b>MmAllocateContiguousMemorySpecifyCache<i>Xxx</i></b> routine.


## -returns



None




## -remarks



The <b>MmFreeContiguousMemorySpecifyCache</b> routine frees a block of physically contiguous memory that was allocated by a previous call to the <a href="..\ntddk\nf-ntddk-mmallocatecontiguousmemoryspecifycache.md">MmAllocateContiguousMemorySpecifyCache</a> or <a href="..\ntddk\nf-ntddk-mmallocatecontiguousmemoryspecifycachenode.md">MmAllocateContiguousMemorySpecifyCacheNode</a> routine. However, <a href="..\ntddk\nf-ntddk-mmfreecontiguousmemory.md">MmFreeContiguousMemory</a> is the preferred routine to use to free memory that was allocated by an <b>MmAllocateContiguousMemorySpecifyCache<i>Xxx</i></b> routine. <b>MmFreeContiguousMemory</b> is faster than <b>MmFreeContiguousMemorySpecifyCache</b> and requires fewer parameters.




## -see-also

<a href="..\ntddk\nf-ntddk-mmallocatecontiguousmemoryspecifycachenode.md">MmAllocateContiguousMemorySpecifyCacheNode</a>



<a href="..\ntddk\nf-ntddk-mmfreecontiguousmemory.md">MmFreeContiguousMemory</a>



<a href="..\ntddk\nf-ntddk-mmallocatecontiguousmemoryspecifycache.md">MmAllocateContiguousMemorySpecifyCache</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmFreeContiguousMemorySpecifyCache routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

