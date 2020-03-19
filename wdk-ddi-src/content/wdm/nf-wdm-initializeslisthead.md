---
UID: NF:wdm.InitializeSListHead
title: InitializeSListHead function (wdm.h)
description: The InitializeSListHead routine (or ExInitializeSListHead) initializes an SLIST_HEADER structure that represents the head of a sequenced singly linked list.
old-location: kernel\exinitializeslisthead.htm
tech.root: kernel
ms.assetid: 258addec-7231-494c-aa70-5966e9a57132
ms.date: 04/30/2018
keywords: ["InitializeSListHead function"]
ms.keywords: ExInitializeSListHead, InitializeSListHead, InitializeSListHead routine [Kernel-Mode Driver Architecture], k102_6d3b712b-2dd5-4962-ad16-a296bdc4de2b.xml, kernel.exinitializeslisthead, wdm/InitializeSListHead
f1_keywords:
 - "wdm/InitializeSListHead"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.irql: Any level (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- InitializeSListHead
product:
- Windows
targetos: Windows
req.typenames: 
---

# InitializeSListHead function


## -description


The <b>InitializeSListHead</b> routine (or ExInitializeSListHead) initializes an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">SLIST_HEADER</a> structure that represents the head of a sequenced singly linked list.


## -parameters




### -param SListHead [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">SLIST_HEADER</a> structure to initialize. The structure must be 16-byte aligned on 64-bit platforms. 


## -remarks



For more information about using this routine to implement a sequenced singly linked list, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists">Singly and Doubly Linked Lists</a>.

Callers of <b>InitializeSListHead or ExInitializeSListHead</b> can be running at any IRQL. If <b>ExInitializeSListHead</b> is called at IRQL >= DISPATCH_LEVEL the storage for <i>SListHead</i> must be resident.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializenpagedlookasidelist">ExInitializeNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializepagedlookasidelist">ExInitializePagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545402">ExInterlockedInsertTailList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinterlockedpopentryslist">ExInterlockedPopEntrySList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinterlockedpushentryslist">ExInterlockedPushEntrySList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exquerydepthslist">ExQueryDepthSList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>
 

 

