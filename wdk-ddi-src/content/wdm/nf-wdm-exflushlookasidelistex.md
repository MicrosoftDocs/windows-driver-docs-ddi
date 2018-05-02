---
UID: NF:wdm.ExFlushLookasideListEx
title: ExFlushLookasideListEx function
author: windows-driver-content
description: The ExFlushLookasideListEx routine flushes all entries from the specified lookaside list and frees the allocated storage for each entry.
old-location: kernel\exflushlookasidelistex.htm
old-project: kernel
ms.assetid: 38601573-750f-46fc-ae04-cef0d90d9ea9
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: ExFlushLookasideListEx, ExFlushLookasideListEx routine [Kernel-Mode Driver Architecture], k102_bb02a725-bc22-4c22-91f2-0232c1cb0f1f.xml, kernel.exflushlookasidelistex, wdm/ExFlushLookasideListEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExFlushLookasideListEx
product: Windows
targetos: Windows
req.typenames: 
---

# ExFlushLookasideListEx function


## -description


The <b>ExFlushLookasideListEx</b> routine flushes all entries from the specified lookaside list and frees the allocated storage for each entry.


## -parameters




### -param Lookaside [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a> structure that describes a lookaside list. This structure was previously initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545298">ExInitializeLookasideListEx</a> routine.


## -returns



None




## -remarks



On return from this routine, the lookaside list is empty and the allocated storage for all its entries has been freed.

For more information about lookaside lists, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545298">ExInitializeLookasideListEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a>
 

 

