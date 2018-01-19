---
UID: NF:wdm.ExDeleteNPagedLookasideList
title: ExDeleteNPagedLookasideList function
author: windows-driver-content
description: The ExDeleteNPagedLookasideList routine destroys a nonpaged lookaside list.
old-location: kernel\exdeletenpagedlookasidelist.htm
old-project: kernel
ms.assetid: c12d4e5f-ec02-405c-91e2-cd5884bb8494
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExDeleteNPagedLookasideList
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
req.alt-api: ExDeleteNPagedLookasideList
req.alt-loc: NtosKrnl.exe
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExDeleteNPagedLookasideList function



## -description
The <b>ExDeleteNPagedLookasideList</b> routine destroys a nonpaged lookaside list.



## -syntax

````
VOID ExDeleteNPagedLookasideList(
  _Inout_ PNPAGED_LOOKASIDE_LIST Lookaside
);
````


## -parameters

### -param Lookaside [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a> structure for the lookaside list, which the caller originally set up with <a href="..\wdm\nf-wdm-exinitializenpagedlookasidelist.md">ExInitializeNPagedLookasideList</a>. 


## -returns
None


## -remarks
<b>ExDeleteNPagedLookasideList</b> is the reciprocal of <b>ExInitializeNPagedLookasideList</b>. It frees any remaining entries in the specified lookaside list and then removes the list from the system-wide set of active lookaside lists.

The caller of <b>ExDeleteNPagedLookasideList</b> is responsible for subsequently releasing the memory that the caller provided to contain the list head.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exinitializenpagedlookasidelist.md">ExInitializeNPagedLookasideList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExDeleteNPagedLookasideList routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

