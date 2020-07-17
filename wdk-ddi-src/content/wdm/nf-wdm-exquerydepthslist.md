---
UID: NF:wdm.ExQueryDepthSList
title: ExQueryDepthSList function (wdm.h)
description: The ExQueryDepthSList routine returns the number of entries currently in a given sequenced singly linked list.
old-location: kernel\exquerydepthslist.htm
tech.root: kernel
ms.assetid: fdf40535-4e0d-4db9-9e95-744029eb2bd5
ms.date: 04/30/2018
keywords: ["ExQueryDepthSList function"]
ms.keywords: ExQueryDepthSList, ExQueryDepthSList routine [Kernel-Mode Driver Architecture], k102_14e2b5cb-bc6a-43f7-a0b2-1fcd8fd414a7.xml, kernel.exquerydepthslist, wdm/ExQueryDepthSList
f1_keywords:
 - "wdm/ExQueryDepthSList"
 - "ExQueryDepthSList"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExQueryDepthSList
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExQueryDepthSList function


## -description


The <b>ExQueryDepthSList</b> routine returns the number of entries currently in a given sequenced singly linked list.


## -parameters




### -param SListHead [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">SLIST_HEADER</a> structure that serves as the header for the sequenced singly linked list. <i>SListHead</i> must have been initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-initializeslisthead">ExInitializeSListHead</a>.


## -returns



<b>ExQueryDepthSList</b> returns the current number of entries in the list.




## -remarks



For more information about using this routine to implement a sequenced singly linked list, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists">Singly and Doubly Linked Lists</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-initializeslisthead">ExInitializeSListHead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinterlockedpopentryslist">ExInterlockedPopEntrySList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinterlockedpushentryslist">ExInterlockedPushEntrySList</a>
 

 

