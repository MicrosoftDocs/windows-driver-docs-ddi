---
UID: NF:wdm.ExAllocateFromNPagedLookasideList
title: ExAllocateFromNPagedLookasideList function
author: windows-driver-content
description: The ExAllocateFromNPagedLookasideList routine returns a pointer to a nonpaged entry from the given lookaside list, or it returns a pointer to a newly allocated nonpaged entry.
old-location: kernel\exallocatefromnpagedlookasidelist.htm
old-project: kernel
ms.assetid: f62c63f0-cf17-4308-97f1-84bb668d2d51
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: ExAllocateFromNPagedLookasideList, ExAllocateFromNPagedLookasideList routine [Kernel-Mode Driver Architecture], k102_43919c0e-8140-4fc8-80f5-1955e39aa493.xml, kernel.exallocatefromnpagedlookasidelist, wdm/ExAllocateFromNPagedLookasideList
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
-	ExAllocateFromNPagedLookasideList
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExAllocateFromNPagedLookasideList function


## -description


The <b>ExAllocateFromNPagedLookasideList</b> routine returns a pointer to a nonpaged entry from the given lookaside list, or it returns a pointer to a newly allocated nonpaged entry. 


## -syntax


````
PVOID ExAllocateFromNPagedLookasideList(
  _Inout_ PNPAGED_LOOKASIDE_LIST Lookaside
);
````


## -parameters




### -param Lookaside [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a> structure for the lookaside list, which the caller already initialized with <a href="..\wdm\nf-wdm-exinitializenpagedlookasidelist.md">ExInitializeNPagedLookasideList</a>. 


## -returns



<b>ExAllocateFromNPagedLookasideList</b> returns a pointer to an entry if one can be allocated. Otherwise, it returns <b>NULL</b>.




## -remarks



If the given lookaside list is not empty, <b>ExAllocateFromNPagedLookasideList</b> removes the first entry from the list and returns a pointer to this entry. Otherwise, <b>ExAllocateFromNPagedLookasideList</b> either calls the <i>Allocate</i> routine specified at list initialization or <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a> to return an entry pointer.

The caller can then set up the returned entry with any caller-determined data. For example, a driver might use each such fixed-size entry to set up command blocks, like SCSI SRBs, to peripheral devices on a particular type of I/O bus. The caller should release each entry with <a href="..\wdm\nf-wdm-exfreetonpagedlookasidelist.md">ExFreeToNPagedLookasideList</a> when it is no longer in use.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.




## -see-also

<a href="..\wdm\nf-wdm-exallocatefrompagedlookasidelist.md">ExAllocateFromPagedLookasideList</a>



<a href="..\wdm\nf-wdm-exfreetonpagedlookasidelist.md">ExFreeToNPagedLookasideList</a>



<a href="..\wdm\nf-wdm-exinitializenpagedlookasidelist.md">ExInitializeNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExAllocateFromNPagedLookasideList routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

