---
UID: NF:wdm.ExInterlockedPopEntrySList
title: ExInterlockedPopEntrySList function
author: windows-driver-content
description: The ExInterlockedPopEntrySList routine atomically removes the first entry from a sequenced singly linked list.
old-location: kernel\exinterlockedpopentryslist.htm
old-project: kernel
ms.assetid: dbea07e1-f987-45d8-91cb-bde45df0672b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExInterlockedPopEntrySList
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
req.alt-api: ExInterlockedPopEntrySList
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
req.irql: Any level (see Remarks section)
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExInterlockedPopEntrySList function



## -description
The <b>ExInterlockedPopEntrySList</b> routine atomically removes the first entry from a sequenced singly linked list.



## -syntax

````
PSLIST_ENTRY ExInterlockedPopEntrySList(
  _Inout_ PSLIST_HEADER ListHead,
  _Inout_ PKSPIN_LOCK   Lock
);
````


## -parameters

### -param ListHead [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a> structure that serves as the header for the sequenced singly linked list. <i>ListHead</i> must have been initialized by calling <a href="..\wdm\nf-wdm-initializeslisthead.md">ExInitializeSListHead</a>.


### -param Lock [in, out]

A pointer to a <b>KSPIN_LOCK</b> structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling <a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>. You must use this spin lock only with the <b>ExInterlocked<i>Xxx</i>List</b> routines.


## -returns
<b>ExInterlockedPopEntrySList</b> returns a pointer to the first <a href="..\wdm\ns-wdm-_slist_entry.md">SLIST_ENTRY</a> structure on the list. If the list was empty, the routine returns <b>NULL</b>.


## -remarks
For more information about using this routine to implement a sequenced singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>. 

On Windows 2000, drivers must use the <b>-D_WIN2K_COMPAT_SLIST_USAGE</b> switch to successfully link code that uses <b>ExInterlockedPopEntrySList</b>.

<b>ExInterlockedPopEntrySList</b> can be called at any IRQL. The storage for the <i>ListHead</i> parameter must be resident at all IRQLs.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-initializeslisthead.md">ExInitializeSListHead</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exinterlockedpushentryslist.md">ExInterlockedPushEntrySList</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exinterlockedremoveheadlist.md">ExInterlockedRemoveHeadList</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exquerydepthslist.md">ExQueryDepthSList</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExInterlockedPopEntrySList routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

