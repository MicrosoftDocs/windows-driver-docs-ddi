---
UID: NF:wdm.ExFreeToPagedLookasideList
title: ExFreeToPagedLookasideList function
author: windows-driver-content
description: The ExFreeToPagedLookasideList routine returns a pageable entry to the given lookaside list or to paged pool.
old-location: kernel\exfreetopagedlookasidelist.htm
old-project: kernel
ms.assetid: b986c7a9-8daa-4957-ad64-2a1f59ed3c68
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExFreeToPagedLookasideList routine [Kernel-Mode Driver Architecture], k102_2d09255c-391a-4937-a991-99d88adf4233.xml, ExFreeToPagedLookasideList, wdm/ExFreeToPagedLookasideList, kernel.exfreetopagedlookasidelist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExFreeToPagedLookasideList
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExFreeToPagedLookasideList function


## -description


The <b>ExFreeToPagedLookasideList</b> routine returns a pageable entry to the given lookaside list or to paged pool.


## -syntax


````
VOID ExFreeToPagedLookasideList(
  _Inout_ PPAGED_LOOKASIDE_LIST Lookaside,
  _In_    PVOID                 Entry
);
````


## -parameters




### -param Lookaside [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a> structure for the lookaside list, which the caller already initialized with <a href="..\wdm\nf-wdm-exinitializepagedlookasidelist.md">ExInitializePagedLookasideList</a>, which the caller already initialized with <b>ExInitializePagedLookasideList</b>.


### -param Entry [in]

A pointer to the entry to be freed. The caller obtained this pointer from a preceding call to <a href="..\wdm\nf-wdm-exallocatefrompagedlookasidelist.md">ExAllocateFromPagedLookasideList</a>. 


## -returns



None




## -remarks



<b>ExFreeToPagedLookasideList</b> is the reciprocal of <b>ExAllocateFromPagedLookasideList</b>. It releases a caller-allocated entry back to the caller's lookaside list or to paged pool when that entry is no longer in use.

The same entry can be reallocated or another entry can be allocated later with a subsequent call to <b>ExAllocateFromPagedLookasideList</b>. The user of a lookaside list can allocate and free such entries dynamically, as needed, until it calls <b>ExDeletePagedLookasideList</b>. <b>ExDeletePagedLookasideList</b> releases any outstanding entries in the list before it clears the system state for the given lookaside list and returns control.

If the specified lookaside list has not yet reached the system-determined maximum number of entries, <b>ExFreeToPagedLookasideList</b> inserts the given entry at the front of the list. Otherwise, the buffer at <i>Entry</i> is released back to paged pool using the caller-supplied <i>Free</i> routine, if any, that was set up when the lookaside list was initialized or <b>ExFreePool</b>.

On Windows 2000, drivers must use the <b>-D_WIN2K_COMPAT_SLIST_USAGE</b> switch to successfully link code that uses <b>ExFreeToPagedLookasideList</b>.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.




## -see-also

<a href="..\wdm\nf-wdm-exallocatefrompagedlookasidelist.md">ExAllocateFromPagedLookasideList</a>



<a href="..\wdm\nf-wdm-exinitializepagedlookasidelist.md">ExInitializePagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a>



<a href="..\wdm\nf-wdm-exdeletepagedlookasidelist.md">ExDeletePagedLookasideList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExFreeToPagedLookasideList routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

