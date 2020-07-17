---
UID: NF:wdm.ExInterlockedPopEntrySList
title: ExInterlockedPopEntrySList function (wdm.h)
description: The ExInterlockedPopEntrySList routine atomically removes the first entry from a sequenced singly linked list.
old-location: kernel\exinterlockedpopentryslist.htm
tech.root: kernel
ms.assetid: dbea07e1-f987-45d8-91cb-bde45df0672b
ms.date: 04/30/2018
keywords: ["ExInterlockedPopEntrySList macro"]
ms.keywords: ExInterlockedPopEntrySList, ExInterlockedPopEntrySList routine [Kernel-Mode Driver Architecture], k102_fc9dbcb7-5cb0-405c-9a65-f7d6b60d2fee.xml, kernel.exinterlockedpopentryslist, wdm/ExInterlockedPopEntrySList
f1_keywords:
 - "wdm/ExInterlockedPopEntrySList"
 - "ExInterlockedPopEntrySList"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExInterlockedPopEntrySList
- ExpInterlockedPopEntrySList
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExInterlockedPopEntrySList macro


## -description


The <b>ExInterlockedPopEntrySList</b> routine atomically removes the first entry from a sequenced singly linked list.

## -syntax

```cpp
NTKERNELAPI
PSLIST_ENTRY
FASTCALL
ExInterlockedPopEntrySList (
    _Inout_ PSLIST_HEADER ListHead,
    _Inout_opt_ _Requires_lock_not_held_(*_Curr_) PKSPIN_LOCK Lock
    );
```

## -parameters




### -param ListHead [in, out]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">SLIST_HEADER</a> structure that serves as the header for the sequenced singly linked list. <i>ListHead</i> must have been initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-initializeslisthead">ExInitializeSListHead</a>.


### -param Lock [in, out]

A pointer to a <b>KSPIN_LOCK</b> structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>. You must use this spin lock only with the <b>ExInterlocked<i>Xxx</i>List</b> routines.




## -remarks

**ExInterlockedPopEntrySList** returns a pointer to the first [**SLIST_ENTRY**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_slist_entry) structure on the list. If the list was empty, the routine returns NULL.


For more information about using this routine to implement a sequenced singly linked list, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists">Singly and Doubly Linked Lists</a>. 

On Windows 2000, drivers must use the <b>-D_WIN2K_COMPAT_SLIST_USAGE</b> switch to successfully link code that uses <b>ExInterlockedPopEntrySList</b>.

<b>ExInterlockedPopEntrySList</b> can be called at any IRQL. The storage for the <i>ListHead</i> parameter must be resident at all IRQLs.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-initializeslisthead">ExInitializeSListHead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinterlockedpushentryslist">ExInterlockedPushEntrySList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545427">ExInterlockedRemoveHeadList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exquerydepthslist">ExQueryDepthSList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>
 

 

