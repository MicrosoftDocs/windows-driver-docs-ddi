---
UID: NF:wdm.ExFreePool
title: ExFreePool function (wdm.h)
description: The ExFreePool routine deallocates a block of pool memory.
old-location: kernel\exfreepool.htm
tech.root: kernel
ms.assetid: c26f9b28-396d-40de-bdc3-287fc3ac4113
ms.date: 04/30/2018
ms.keywords: ExFreePool, ExFreePool routine [Kernel-Mode Driver Architecture], k102_134b475a-f669-4f1e-8836-f41945d7230c.xml, kernel.exfreepool, wdm/ExFreePool
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExFreePool
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExFreePool function


## -description


The <b>ExFreePool</b> routine deallocates a block of pool memory. 


## -parameters




#### - P [in]

Specifies the address of the block of pool memory being deallocated. 


## -returns



None




## -remarks



This routine releases memory allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff544501">ExAllocatePool</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544506">ExAllocatePoolWithQuota</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff544513">ExAllocatePoolWithQuotaTag</a>. The memory block must not be accessed after it is freed.

Drivers can also use the <b>ExFreePoolWithTag</b> routine to free buffers allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff544513">ExAllocatePoolWithQuotaTag</a>.

Callers of <b>ExFreePool</b> must be running at IRQL &lt;= DISPATCH_LEVEL. A caller at DISPATCH_LEVEL must have specified a <b>NonPaged</b><i>Xxx</i><i>PoolType</i> when the memory was allocated. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544501">ExAllocatePool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544506">ExAllocatePoolWithQuota</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544513">ExAllocatePoolWithQuotaTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544593">ExFreePoolWithTag</a>
 

 

