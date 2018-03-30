---
UID: NF:wdm.ExFreePoolWithTag
title: ExFreePoolWithTag function
author: windows-driver-content
description: The ExFreePoolWithTag routine deallocates a block of pool memory allocated with the specified tag.
old-location: kernel\exfreepoolwithtag.htm
old-project: kernel
ms.assetid: ebf404dd-479a-4573-9372-4b777c3cd5e7
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ExFreePoolWithTag, ExFreePoolWithTag routine [Kernel-Mode Driver Architecture], k102_03ac2997-acff-40b6-a110-718261627130.xml, kernel.exfreepoolwithtag, wdm/ExFreePoolWithTag
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
req.ddi-compliance: IrqlExFree1, IrqlExFree2, IrqlExFree3
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
-	ExFreePoolWithTag
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExFreePoolWithTag function


## -description


The <b>ExFreePoolWithTag</b> routine deallocates a block of pool memory allocated with the specified tag.


## -parameters




### -param P [in]

Specifies the beginning address of a block of pool memory allocated by either <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff544513">ExAllocatePoolWithQuotaTag</a>.


### -param Tag [in]

Specifies the tag value passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff544513">ExAllocatePoolWithQuotaTag</a> when the block of memory was originally allocated.


## -returns



None




## -remarks



Callers of <b>ExFreePoolWithTag</b> must be running at IRQL &lt;= DISPATCH_LEVEL. A caller at DISPATCH_LEVEL must have specified a <b>NonPaged</b><i>Xxx</i><i>PoolType</i> when the memory was allocated. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544513">ExAllocatePoolWithQuotaTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a>
 

 

