---
UID: NF:wdm.ExAllocateFromLookasideListEx
title: ExAllocateFromLookasideListEx function
author: windows-driver-content
description: The ExAllocateFromLookasideListEx routine removes the first entry from the specified lookaside list, or, if the list is empty, dynamically allocates the storage for a new entry.
old-location: kernel\exallocatefromlookasidelistex.htm
old-project: kernel
ms.assetid: 70782045-7026-4771-8072-9057fc31a642
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k102_d3c72529-8c0d-48bf-8b5f-dc19d801bf8f.xml, ExAllocateFromLookasideListEx, wdm/ExAllocateFromLookasideListEx, kernel.exallocatefromlookasidelistex, ExAllocateFromLookasideListEx routine [Kernel-Mode Driver Architecture]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExAllocateFromLookasideListEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExAllocateFromLookasideListEx function


## -description


The <b>ExAllocateFromLookasideListEx</b> routine removes the first entry from the specified lookaside list, or, if the list is empty, dynamically allocates the storage for a new entry.


## -syntax


````
PVOID ExAllocateFromLookasideListEx(
  _Inout_ PLOOKASIDE_LIST_EX Lookaside
);
````


## -parameters




#### - Lookaside [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a> structure that describes a lookaside list. This structure was previously initialized by the <a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a> routine. 


## -returns


<b>ExAllocateFromLookasideListEx</b> returns a pointer to a lookaside-list entry, if an entry is available in the list or can be dynamically allocated. Otherwise, this routine returns <b>NULL</b>. 



## -remarks


This routine removes the first entry, if an entry is available, from the specified lookaside list and returns a pointer to this entry. If the list is empty, the routine allocates storage for a new entry and returns a pointer to this entry. If this allocation fails, the routine returns <b>NULL</b>.

If the lookaside list is empty, <b>ExAllocateFromLookasideListEx</b> calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554322">LookasideListAllocateEx</a> routine to allocate storage for a new entry, if the driver has provided such a routine. Otherwise, a default allocation routine is used to allocate the entry.

After the caller finishes using the entry, it should free the entry by calling the <a href="..\wdm\nf-wdm-exfreetolookasidelistex.md">ExFreeToLookasideListEx</a> routine.

In the current implementation, a lookaside list operates as a last-in, first-out (LIFO) stack. Thus, the last entry to be freed (and pushed onto the stack) is the next entry to be allocated (popped) from the list.

For more information about lookaside lists, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554322">LookasideListAllocateEx</a>

<a href="..\wdm\nf-wdm-exfreetolookasidelistex.md">ExFreeToLookasideListEx</a>

<a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExAllocateFromLookasideListEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

