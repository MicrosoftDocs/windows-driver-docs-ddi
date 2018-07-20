---
UID: NF:wdm.ExInterlockedPushEntrySList
title: ExInterlockedPushEntrySList macro
author: windows-driver-content
description: The ExInterlockedPushEntrySList routine atomically inserts an entry at the beginning of a sequenced singly linked list.
old-location: kernel\exinterlockedpushentryslist.htm
old-project: kernel
ms.assetid: 4bff45b5-c295-444d-82ea-59cfd6c37551
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: ExInterlockedPushEntrySList, ExInterlockedPushEntrySList routine [Kernel-Mode Driver Architecture], k102_53da8507-cae3-4a71-9c59-49676a8b7a95.xml, kernel.exinterlockedpushentryslist, wdm/ExInterlockedPushEntrySList
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExInterlockedPushEntrySList
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExInterlockedPushEntrySList macro


## -description


The <b>ExInterlockedPushEntrySList</b> routine atomically inserts an entry at the beginning of a sequenced singly linked list.


## -parameters




### -param Head


A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a> structure that serves as the header for the sequenced singly linked list. <i>ListHead</i> must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545321">ExInitializeSListHead</a>.


### -param Entry

A pointer to the caller-allocated entry to be inserted. 


### -param Lock [in, out]

A pointer to a <b>KSPIN_LOCK</b> structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff552160">KeInitializeSpinLock</a>. You must use this spin lock only with the <b>ExInterlocked<i>Xxx</i>List</b> routines.



## -remarks



For more information about using this routine to implement a sequenced singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

On Windows 2000, drivers must use the <b>-D_WIN2K_COMPAT_SLIST_USAGE</b> switch to successfully link code that uses <b>ExInterlockedPushEntrySList</b>.

The <b>ExInterlockedPushEntrySList</b> routine can be called at any IRQL. The storage for the <i>ListHead</i> parameter and the list entries must be resident at all IRQLs.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545321">ExInitializeSListHead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545402">ExInterlockedInsertTailList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545414">ExInterlockedPopEntrySList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545502">ExQueryDepthSList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552160">KeInitializeSpinLock</a>
 

 

