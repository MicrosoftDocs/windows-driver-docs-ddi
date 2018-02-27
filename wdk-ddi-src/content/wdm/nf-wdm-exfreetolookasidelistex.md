---
UID: NF:wdm.ExFreeToLookasideListEx
title: ExFreeToLookasideListEx function
author: windows-driver-content
description: The ExFreeToLookasideListEx routine inserts an entry into a lookaside list, or, if the list is full, frees the allocated storage for the entry.
old-location: kernel\exfreetolookasidelistex.htm
old-project: kernel
ms.assetid: 37057400-7f4d-4274-b1ef-f03771cae34f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ExFreeToLookasideListEx, ExFreeToLookasideListEx routine [Kernel-Mode Driver Architecture], k102_2d275628-4a0f-4da8-a512-60a0998d8c5b.xml, kernel.exfreetolookasidelistex, wdm/ExFreeToLookasideListEx
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
-	ExFreeToLookasideListEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExFreeToLookasideListEx function


## -description


The <b>ExFreeToLookasideListEx</b> routine inserts an entry into a lookaside list, or, if the list is full, frees the allocated storage for the entry. 


## -syntax


````
VOID ExFreeToLookasideListEx(
  _Inout_ PLOOKASIDE_LIST_EX Lookaside,
  _In_    PVOID              Entry
);
````


## -parameters




### -param Lookaside [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a> structure that describes a lookaside list. This structure was previously initialized by the <a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a> routine. 


### -param Entry [in]

A pointer to the lookaside-list entry that is being freed.


## -returns



None




## -remarks



This routine frees a lookaside-list entry that was allocated by a previous call to the <a href="..\wdm\nf-wdm-exallocatefromlookasidelistex.md">ExAllocateFromLookasideListEx</a> routine. <b>ExFreeToLookasideListEx</b> inserts the entry into the specified lookaside list, if space for the entry is available in the list. If the list is full (that is, it already contains the maximum number of entries, as determined by the operating system), <b>ExFreeToLookasideListEx</b> calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554324">LookasideListFreeEx</a> routine to free the storage for the specified entry, if the driver has provided such a routine. Otherwise, a default deallocation routine is used to free the entry.

For more information about lookaside lists, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a>



<a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a>



<a href="..\wdm\nf-wdm-exallocatefromlookasidelistex.md">ExAllocateFromLookasideListEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExFreeToLookasideListEx routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

