---
UID: NF:wdm.ExDeleteNPagedLookasideList
title: ExDeleteNPagedLookasideList function (wdm.h)
description: The ExDeleteNPagedLookasideList routine destroys a nonpaged lookaside list.
old-location: kernel\exdeletenpagedlookasidelist.htm
tech.root: kernel
ms.assetid: c12d4e5f-ec02-405c-91e2-cd5884bb8494
ms.date: 04/30/2018
keywords: ["ExDeleteNPagedLookasideList function"]
ms.keywords: ExDeleteNPagedLookasideList, ExDeleteNPagedLookasideList routine [Kernel-Mode Driver Architecture], k102_401f2550-ef71-4199-be7f-cdd7652a2c03.xml, kernel.exdeletenpagedlookasidelist, wdm/ExDeleteNPagedLookasideList
f1_keywords:
 - "wdm/ExDeleteNPagedLookasideList"
 - "ExDeleteNPagedLookasideList"
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
- ExDeleteNPagedLookasideList
targetos: Windows
req.typenames: 
---

# ExDeleteNPagedLookasideList function


## -description


The <b>ExDeleteNPagedLookasideList</b> routine destroys a nonpaged lookaside list.


## -parameters




### -param Lookaside 
[in, out]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">NPAGED_LOOKASIDE_LIST</a> structure for the lookaside list, which the caller originally set up with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializenpagedlookasidelist">ExInitializeNPagedLookasideList</a>. 


## -remarks



<b>ExDeleteNPagedLookasideList</b> is the reciprocal of <b>ExInitializeNPagedLookasideList</b>. It frees any remaining entries in the specified lookaside list and then removes the list from the system-wide set of active lookaside lists.

The caller of <b>ExDeleteNPagedLookasideList</b> is responsible for subsequently releasing the memory that the caller provided to contain the list head.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-lookaside-lists">Using Lookaside Lists</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializenpagedlookasidelist">ExInitializeNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">NPAGED_LOOKASIDE_LIST</a>
 

 

