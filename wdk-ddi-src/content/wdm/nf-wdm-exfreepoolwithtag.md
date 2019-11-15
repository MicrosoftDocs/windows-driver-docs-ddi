---
UID: NF:wdm.ExFreePoolWithTag
title: ExFreePoolWithTag function (wdm.h)
description: The ExFreePoolWithTag routine deallocates a block of pool memory allocated with the specified tag.
old-location: kernel\exfreepoolwithtag.htm
tech.root: kernel
ms.assetid: ebf404dd-479a-4573-9372-4b777c3cd5e7
ms.date: 04/30/2018
ms.keywords: ExFreePoolWithTag, ExFreePoolWithTag routine [Kernel-Mode Driver Architecture], k102_03ac2997-acff-40b6-a110-718261627130.xml, kernel.exfreepoolwithtag, wdm/ExFreePoolWithTag
ms.topic: function
f1_keywords:
 - "wdm/ExFreePoolWithTag"
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExFreePoolWithTag
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExFreePoolWithTag function


## -description


The <b>ExFreePoolWithTag</b> routine deallocates a block of pool memory allocated with the specified tag.


## -parameters




### -param P [in]

Specifies the beginning address of a block of pool memory allocated by either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithquotatag">ExAllocatePoolWithQuotaTag</a>.


### -param Tag [in]

Specifies the tag value passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithquotatag">ExAllocatePoolWithQuotaTag</a> when the block of memory was originally allocated.

The tag is a non-zero character literal of one to to four characters delimited by single quotation marks (for example, 'Tag1'). The string is usually specified in reverse order (for example, '1gaT'). Each ASCII character in the tag must be a value in the range 0x20 (space) to 0x7E (tilde). Each allocation code path should use a unique pool tag to help debuggers and verifiers identify the code path.

## -remarks



Callers of <b>ExFreePoolWithTag</b> must be running at IRQL <= DISPATCH_LEVEL. A caller at DISPATCH_LEVEL must have specified a <b>NonPaged</b><i>Xxx</i><i>PoolType</i> when the memory was allocated. Otherwise, the caller must be running at IRQL <= APC_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithquotatag">ExAllocatePoolWithQuotaTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>
 

 

