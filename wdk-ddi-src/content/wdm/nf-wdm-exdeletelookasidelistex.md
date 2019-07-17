---
UID: NF:wdm.ExDeleteLookasideListEx
title: ExDeleteLookasideListEx function (wdm.h)
description: The ExDeleteLookasideListEx routine deletes a lookaside list.
old-location: kernel\exdeletelookasidelistex.htm
tech.root: kernel
ms.assetid: b72187de-a2ac-446f-bb06-9ca380454122
ms.date: 04/30/2018
ms.keywords: ExDeleteLookasideListEx, ExDeleteLookasideListEx routine [Kernel-Mode Driver Architecture], k102_35b6c2b4-58a3-4900-b8dc-63ed0a53b80f.xml, kernel.exdeletelookasidelistex, wdm/ExDeleteLookasideListEx
ms.topic: function
f1_keywords:
 - "wdm/ExDeleteLookasideListEx"
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExDeleteLookasideListEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExDeleteLookasideListEx function


## -description


The <b>ExDeleteLookasideListEx</b> routine deletes a lookaside list. 


## -parameters




### -param Lookaside [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">LOOKASIDE_LIST_EX</a> structure that describes a lookaside list. This structure was previously initialized by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exinitializelookasidelistex">ExInitializeLookasideListEx</a> routine. 


## -returns



None




## -remarks



<b>ExDeleteLookasideListEx</b> is the reciprocal of the <b>ExInitializeLookasideListEx</b> routine. It frees any remaining entries in the specified lookaside list and then removes the list from the system-wide set of active lookaside lists.

On return from <b>ExDeleteLookasideListEx</b>, the caller is responsible for releasing, if necessary, the caller-supplied storage for the <b>LOOKASIDE_LIST_EX</b> structure.

For more information about lookaside lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-lookaside-lists">Using Lookaside Lists</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exinitializelookasidelistex">ExInitializeLookasideListEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">LOOKASIDE_LIST_EX</a>
 

 

