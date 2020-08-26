---
UID: NF:wdm.ExFlushLookasideListEx
title: ExFlushLookasideListEx function (wdm.h)
description: The ExFlushLookasideListEx routine flushes all entries from the specified lookaside list and frees the allocated storage for each entry.
old-location: kernel\exflushlookasidelistex.htm
tech.root: kernel
ms.assetid: 38601573-750f-46fc-ae04-cef0d90d9ea9
ms.date: 04/30/2018
keywords: ["ExFlushLookasideListEx function"]
ms.keywords: ExFlushLookasideListEx, ExFlushLookasideListEx routine [Kernel-Mode Driver Architecture], k102_bb02a725-bc22-4c22-91f2-0232c1cb0f1f.xml, kernel.exflushlookasidelistex, wdm/ExFlushLookasideListEx
f1_keywords:
 - "wdm/ExFlushLookasideListEx"
 - "ExFlushLookasideListEx"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
- ExFlushLookasideListEx
targetos: Windows
req.typenames: 
---

# ExFlushLookasideListEx function


## -description


The <b>ExFlushLookasideListEx</b> routine flushes all entries from the specified lookaside list and frees the allocated storage for each entry.


## -parameters




### -param Lookaside 
[in, out]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">LOOKASIDE_LIST_EX</a> structure that describes a lookaside list. This structure was previously initialized by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializelookasidelistex">ExInitializeLookasideListEx</a> routine.


## -remarks



On return from this routine, the lookaside list is empty and the allocated storage for all its entries has been freed.

For more information about lookaside lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-lookaside-lists">Using Lookaside Lists</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializelookasidelistex">ExInitializeLookasideListEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">LOOKASIDE_LIST_EX</a>
 

 

