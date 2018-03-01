---
UID: NF:wdm.ExFreePoolWithTag
title: ExFreePoolWithTag function
author: windows-driver-content
description: The ExFreePoolWithTag routine deallocates a block of pool memory allocated with the specified tag.
old-location: kernel\exfreepoolwithtag.htm
old-project: kernel
ms.assetid: ebf404dd-479a-4573-9372-4b777c3cd5e7
ms.author: windowsdriverdev
ms.date: 2/24/2018
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


## -syntax


````
VOID ExFreePoolWithTag(
  _In_ PVOID P,
  _In_ ULONG Tag
);
````


## -parameters




### -param P [in]

Specifies the beginning address of a block of pool memory allocated by either <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a> or <a href="..\wdm\nf-wdm-exallocatepoolwithquotatag.md">ExAllocatePoolWithQuotaTag</a>.


### -param Tag [in]

Specifies the tag value passed to <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a> or <a href="..\wdm\nf-wdm-exallocatepoolwithquotatag.md">ExAllocatePoolWithQuotaTag</a> when the block of memory was originally allocated.


## -returns



None




## -remarks



Callers of <b>ExFreePoolWithTag</b> must be running at IRQL &lt;= DISPATCH_LEVEL. A caller at DISPATCH_LEVEL must have specified a <b>NonPaged</b><i>Xxx</i><i>PoolType</i> when the memory was allocated. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.




## -see-also

<a href="..\wdm\nf-wdm-exallocatepoolwithquotatag.md">ExAllocatePoolWithQuotaTag</a>



<a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>



<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExFreePoolWithTag routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

