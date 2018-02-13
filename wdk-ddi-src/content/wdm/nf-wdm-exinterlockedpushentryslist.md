---
UID: NF:wdm.ExInterlockedPushEntrySList
title: ExInterlockedPushEntrySList macro
author: windows-driver-content
description: The ExInterlockedPushEntrySList routine atomically inserts an entry at the beginning of a sequenced singly linked list.
old-location: kernel\exinterlockedpushentryslist.htm
old-project: kernel
ms.assetid: 4bff45b5-c295-444d-82ea-59cfd6c37551
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExInterlockedPushEntrySList routine [Kernel-Mode Driver Architecture], k102_53da8507-cae3-4a71-9c59-49676a8b7a95.xml, wdm/ExInterlockedPushEntrySList, ExInterlockedPushEntrySList, kernel.exinterlockedpushentryslist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
req.irql: Any level (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExInterlockedPushEntrySList
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExInterlockedPushEntrySList macro


## -description


The <b>ExInterlockedPushEntrySList</b> routine atomically inserts an entry at the beginning of a sequenced singly linked list.


## -syntax


````
PSLIST_ENTRY ExInterlockedPushEntrySList(
  _Inout_ PSLIST_HEADER ListHead,
  _Inout_ PSLIST_ENTRY  ListEntry,
  _Inout_ PKSPIN_LOCK   Lock
);
````


## -parameters




### -param Head

TBD


### -param Entry

TBD


### -param Lock [in, out]

A pointer to a <b>KSPIN_LOCK</b> structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling <a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>. You must use this spin lock only with the <b>ExInterlocked<i>Xxx</i>List</b> routines.


#### - ListHead [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a> structure that serves as the header for the sequenced singly linked list. <i>ListHead</i> must have been initialized by calling <a href="..\wdm\nf-wdm-initializeslisthead.md">ExInitializeSListHead</a>.


#### - ListEntry [in, out]

A pointer to the caller-allocated entry to be inserted. 


## -remarks



For more information about using this routine to implement a sequenced singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

On Windows 2000, drivers must use the <b>-D_WIN2K_COMPAT_SLIST_USAGE</b> switch to successfully link code that uses <b>ExInterlockedPushEntrySList</b>.

The <b>ExInterlockedPushEntrySList</b> routine can be called at any IRQL. The storage for the <i>ListHead</i> parameter and the list entries must be resident at all IRQLs.




## -see-also

<a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>



<a href="..\wdm\nf-wdm-exquerydepthslist.md">ExQueryDepthSList</a>



<a href="..\wdm\nf-wdm-exinterlockedpopentryslist.md">ExInterlockedPopEntrySList</a>



<a href="..\wdm\nf-wdm-initializeslisthead.md">ExInitializeSListHead</a>



<a href="..\wdm\nf-wdm-exinterlockedinserttaillist.md">ExInterlockedInsertTailList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExInterlockedPushEntrySList routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

