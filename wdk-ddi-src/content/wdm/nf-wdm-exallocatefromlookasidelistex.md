---
UID: NF:wdm.ExAllocateFromLookasideListEx
title: ExAllocateFromLookasideListEx function
author: windows-driver-content
description: The ExAllocateFromLookasideListEx routine removes the first entry from the specified lookaside list, or, if the list is empty, dynamically allocates the storage for a new entry.
old-location: kernel\exallocatefromlookasidelistex.htm
tech.root: kernel
ms.assetid: 70782045-7026-4771-8072-9057fc31a642
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: ExAllocateFromLookasideListEx, ExAllocateFromLookasideListEx routine [Kernel-Mode Driver Architecture], k102_d3c72529-8c0d-48bf-8b5f-dc19d801bf8f.xml, kernel.exallocatefromlookasidelistex, wdm/ExAllocateFromLookasideListEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
-	ExAllocateFromLookasideListEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExAllocateFromLookasideListEx function


## -description


The <b>ExAllocateFromLookasideListEx</b> routine removes the first entry from the specified lookaside list, or, if the list is empty, dynamically allocates the storage for a new entry.


## -parameters




### -param Lookaside [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a> structure that describes a lookaside list. This structure was previously initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545298">ExInitializeLookasideListEx</a> routine. 


## -returns



<b>ExAllocateFromLookasideListEx</b> returns a pointer to a lookaside-list entry, if an entry is available in the list or can be dynamically allocated. Otherwise, this routine returns <b>NULL</b>. 




## -remarks



This routine removes the first entry, if an entry is available, from the specified lookaside list and returns a pointer to this entry. If the list is empty, the routine allocates storage for a new entry and returns a pointer to this entry. If this allocation fails, the routine returns <b>NULL</b>.

If the lookaside list is empty, <b>ExAllocateFromLookasideListEx</b> calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554322">LookasideListAllocateEx</a> routine to allocate storage for a new entry, if the driver has provided such a routine. Otherwise, a default allocation routine is used to allocate the entry.

After the caller finishes using the entry, it should free the entry by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544597">ExFreeToLookasideListEx</a> routine.

In the current implementation, a lookaside list operates as a last-in, first-out (LIFO) stack. Thus, the last entry to be freed (and pushed onto the stack) is the next entry to be allocated (popped) from the list.

For more information about lookaside lists, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544597">ExFreeToLookasideListEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545298">ExInitializeLookasideListEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554322">LookasideListAllocateEx</a>
 

 

