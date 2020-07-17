---
UID: NF:wdm.ExDeletePagedLookasideList
title: ExDeletePagedLookasideList function (wdm.h)
description: The ExDeletePagedLookasideList routine destroys a paged lookaside list.
old-location: kernel\exdeletepagedlookasidelist.htm
tech.root: kernel
ms.assetid: da3784a8-6fc5-47cc-932e-52ec16392e49
ms.date: 04/30/2018
keywords: ["ExDeletePagedLookasideList function"]
ms.keywords: ExDeletePagedLookasideList, ExDeletePagedLookasideList routine [Kernel-Mode Driver Architecture], k102_6e78a15a-e6e1-4282-a8de-a4f38f74ebc6.xml, kernel.exdeletepagedlookasidelist, wdm/ExDeletePagedLookasideList
f1_keywords:
 - "wdm/ExDeletePagedLookasideList"
 - "ExDeletePagedLookasideList"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExDeletePagedLookasideList
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExDeletePagedLookasideList function


## -description


The <b>ExDeletePagedLookasideList</b> routine destroys a paged lookaside list.


## -parameters




### -param Lookaside [in, out]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">PAGED_LOOKASIDE_LIST</a> structure for the lookaside list, which the caller already initialized with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializepagedlookasidelist">ExInitializePagedLookasideList</a>, which the caller originally set up with <b>ExInitializePagedLookasideList</b>. 


## -remarks



<b>ExDeletePagedLookasideList</b> is the reciprocal of <b>ExInitializePagedLookasideList</b>. It frees any remaining entries in the specified lookaside list and then removes the list from the system-wide set of active lookaside lists. 

The caller of <b>ExDeletePagedLookasideList</b> is responsible for subsequently releasing the memory that the caller provided to contain the list head.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-lookaside-lists">Using Lookaside Lists</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializepagedlookasidelist">ExInitializePagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">PAGED_LOOKASIDE_LIST</a>
 

 

