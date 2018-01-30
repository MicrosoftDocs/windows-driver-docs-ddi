---
UID: NF:wdm.ExFreePool
title: ExFreePool function
author: windows-driver-content
description: The ExFreePool routine deallocates a block of pool memory.
old-location: kernel\exfreepool.htm
old-project: kernel
ms.assetid: c26f9b28-396d-40de-bdc3-287fc3ac4113
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExFreePool, kernel.exfreepool, wdm/ExFreePool, ExFreePool routine [Kernel-Mode Driver Architecture], k102_134b475a-f669-4f1e-8836-f41945d7230c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: DoubleExFreePool
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExFreePool
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExFreePool function


## -description


The <b>ExFreePool</b> routine deallocates a block of pool memory. 


## -syntax


````
VOID ExFreePool(
  _In_ PVOID P
);
````


## -parameters




#### - P [in]

Specifies the address of the block of pool memory being deallocated. 


## -returns


None



## -remarks


This routine releases memory allocated by <a href="..\wdm\nf-wdm-exallocatepool.md">ExAllocatePool</a>, <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>, <a href="..\wdm\nf-wdm-exallocatepoolwithquota.md">ExAllocatePoolWithQuota</a>, or <a href="..\wdm\nf-wdm-exallocatepoolwithquotatag.md">ExAllocatePoolWithQuotaTag</a>. The memory block must not be accessed after it is freed.

Drivers can also use the <b>ExFreePoolWithTag</b> routine to free buffers allocated by <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a> and <a href="..\wdm\nf-wdm-exallocatepoolwithquotatag.md">ExAllocatePoolWithQuotaTag</a>.

Callers of <b>ExFreePool</b> must be running at IRQL &lt;= DISPATCH_LEVEL. A caller at DISPATCH_LEVEL must have specified a <b>NonPaged</b><i>Xxx</i><i>PoolType</i> when the memory was allocated. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.



## -see-also

<a href="..\wdm\nf-wdm-exallocatepoolwithquota.md">ExAllocatePoolWithQuota</a>

<a href="..\wdm\nf-wdm-exallocatepoolwithquotatag.md">ExAllocatePoolWithQuotaTag</a>

<a href="..\wdm\nf-wdm-exfreepoolwithtag.md">ExFreePoolWithTag</a>

<a href="..\wdm\nf-wdm-exallocatepool.md">ExAllocatePool</a>

<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExFreePool routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

