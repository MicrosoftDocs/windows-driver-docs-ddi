---
UID: NF:wdm.ExFreeToNPagedLookasideList
title: ExFreeToNPagedLookasideList function
author: windows-driver-content
description: The ExFreeToNPagedLookasideList routine returns a nonpaged entry to the given lookaside list or to nonpaged pool.
old-location: kernel\exfreetonpagedlookasidelist.htm
old-project: kernel
ms.assetid: 8abd72f1-0537-4624-b3d4-2de51c4d4daa
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.exfreetonpagedlookasidelist, ExFreeToNPagedLookasideList routine [Kernel-Mode Driver Architecture], ExFreeToNPagedLookasideList, wdm/ExFreeToNPagedLookasideList, k102_30577c54-40a4-41a3-abc2-f3cdcd45ef1b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: SpIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	ExFreeToNPagedLookasideList
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExFreeToNPagedLookasideList function


## -description


The <b>ExFreeToNPagedLookasideList</b> routine returns a nonpaged entry to the given lookaside list or to nonpaged pool.


## -syntax


````
 VOID ExFreeToNPagedLookasideList(
  _Inout_ PNPAGED_LOOKASIDE_LIST Lookaside,
  _In_    PVOID                  Entry
);
````


## -parameters




### -param Lookaside [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a> structure for the lookaside list, which the caller already initialized with <a href="..\wdm\nf-wdm-exinitializenpagedlookasidelist.md">ExInitializeNPagedLookasideList</a>. 


### -param Entry [in]

A pointer to the entry to be freed. The caller obtained this pointer from a preceding call to <a href="..\wdm\nf-wdm-exallocatefromnpagedlookasidelist.md">ExAllocateFromNPagedLookasideList</a>. 


## -returns


None



## -remarks


<b>ExFreeToNPagedLookasideList</b> is the reciprocal of <b>ExAllocateFromNPagedLookasideList</b>. It releases a caller-allocated entry back to the caller's lookaside list or to nonpaged pool when that entry is no longer in use.

The same entry can be reallocated or another entry allocated later with a subsequent call to <b>ExAllocateFromNPagedLookasideList</b>. The user of the lookaside list can allocate and free such entries dynamically on an as-needed basis until it calls <b>ExDeleteNPagedLookasideList</b>, which releases any outstanding entries in the list before it clears the system state for the given lookaside list and returns control.

If the specified lookaside list has not yet reached the system-determined maximum number of entries, <b>ExFreeToNPagedLookasideList</b> inserts the given entry at the front of the list. Otherwise, the buffer at <i>Entry</i> is released to nonpaged pool using the caller-supplied <i>Free</i> routine, if any, that was set up when the lookaside list was initialized or <b>ExFreePool</b>.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a>

<a href="..\wdm\nf-wdm-exdeletenpagedlookasidelist.md">ExDeleteNPagedLookasideList</a>

<a href="..\wdm\nf-wdm-exallocatefromnpagedlookasidelist.md">ExAllocateFromNPagedLookasideList</a>

<a href="..\wdm\nf-wdm-exinitializenpagedlookasidelist.md">ExInitializeNPagedLookasideList</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExFreeToNPagedLookasideList routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

