---
UID: NF:wdm.ExAllocateFromPagedLookasideList
title: ExAllocateFromPagedLookasideList function
author: windows-driver-content
description: The ExAllocateFromPagedLookasideList routine returns a pointer to a paged entry from the given lookaside list, or it returns a pointer to a newly allocated paged entry.
old-location: kernel\exallocatefrompagedlookasidelist.htm
old-project: kernel
ms.assetid: f0c86720-4914-47b1-abb1-151196cc2a68
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , A, E, ExAllocateFromPagedLookasideList, ExAllocateFromPagedLookasideList routine [Kernel-Mode Driver Architecture], F, L, P, a, c, d, e, g, i, k, k102_96e03fc6-f951-4c96-8de4-32d67e85ec02.xml, kernel.exallocatefrompagedlookasidelist, l, m, o, r, s, t, wdm/ExAllocateFromPagedLookasideList, x"
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
-	ExAllocateFromPagedLookasideList
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExAllocateFromPagedLookasideList function


## -description


The <b>ExAllocateFromPagedLookasideList</b> routine returns a pointer to a paged entry from the given lookaside list, or it returns a pointer to a newly allocated paged entry. 


## -syntax


````
PVOID ExAllocateFromPagedLookasideList(
  _Inout_ PPAGED_LOOKASIDE_LIST Lookaside
);
````


## -parameters




### -param Lookaside [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a> structure for the lookaside list, which the caller already initialized with <a href="..\wdm\nf-wdm-exinitializepagedlookasidelist.md">ExInitializePagedLookasideList</a>. 


## -returns



<b>ExAllocateFromPagedLookasideList</b> returns a pointer to an entry if one can be allocated. Otherwise, it returns <b>NULL</b>.




## -remarks



If the given lookaside list is not empty, <b>ExAllocateFromPagedLookasideList</b> removes the first entry from the list and returns a pointer to this entry. Otherwise, <b>ExAllocateFromPagedLookasideList</b> either calls the <i>Allocate</i> routine specified at list initialization or <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a> to return an entry pointer.

The caller can then set up the returned entry with any caller-determined data. The caller should release each entry with <a href="..\wdm\nf-wdm-exfreetopagedlookasidelist.md">ExFreeToPagedLookasideList</a> when it is no longer in use. 

Because the entries in a paged lookaside list are allocated from pageable memory, they must not be accessed at an IRQL &gt;= DISPATCH_LEVEL. You can use <a href="..\wdm\nf-wdm-exallocatefromnpagedlookasidelist.md">ExAllocateFromNPagedLookasideList</a> to create a lookaside list with non-pageable entries.

On Windows 2000, drivers must use the <b>-D_WIN2K_COMPAT_SLIST_USAGE</b> switch to successfully link code that uses <b>ExAllocateFromPagedLookasideList</b>.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a>



<a href="..\wdm\nf-wdm-exinitializepagedlookasidelist.md">ExInitializePagedLookasideList</a>



<a href="..\wdm\nf-wdm-exfreetopagedlookasidelist.md">ExFreeToPagedLookasideList</a>



<a href="..\wdm\nf-wdm-exallocatefromnpagedlookasidelist.md">ExAllocateFromNPagedLookasideList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExAllocateFromPagedLookasideList routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

