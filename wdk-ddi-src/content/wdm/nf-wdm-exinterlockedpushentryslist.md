---
UID: NF:wdm.ExInterlockedPushEntrySList
title: ExInterlockedPushEntrySList macro (wdm.h)
description: The ExInterlockedPushEntrySList routine atomically inserts an entry at the beginning of a sequenced singly linked list.
old-location: kernel\exinterlockedpushentryslist.htm
tech.root: kernel
ms.assetid: 4bff45b5-c295-444d-82ea-59cfd6c37551
ms.date: 04/30/2018
keywords: ["ExInterlockedPushEntrySList macro"]
ms.keywords: ExInterlockedPushEntrySList, ExInterlockedPushEntrySList routine [Kernel-Mode Driver Architecture], k102_53da8507-cae3-4a71-9c59-49676a8b7a95.xml, kernel.exinterlockedpushentryslist, wdm/ExInterlockedPushEntrySList
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ExInterlockedPushEntrySList
 - wdm/ExInterlockedPushEntrySList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExInterlockedPushEntrySList
 - ExpInterlockedPushEntrySList
---

# ExInterlockedPushEntrySList macro


## -description

The <b>ExInterlockedPushEntrySList</b> routine atomically inserts an entry at the beginning of a sequenced singly linked list.

## -parameters

### -param ListHead

A pointer to the <a href="/windows-hardware/drivers/kernel/eprocess">SLIST_HEADER</a> structure that serves as the header for the sequenced singly linked list. <i>ListHead</i> must have been initialized by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-initializeslisthead">ExInitializeSListHead</a>.

### -param ListEntry

A pointer to the caller-allocated entry to be inserted.

### -param Lock 

[in, out]
A pointer to a <b>KSPIN_LOCK</b> structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>. You must use this spin lock only with the <b>ExInterlocked<i>Xxx</i>List</b> routines.

## -syntax

```cpp
NTKERNELAPI
PSLIST_ENTRY
FASTCALL
ExInterlockedPushEntrySList (
    _Inout_ PSLIST_HEADER ListHead,
    _Inout_ __drv_aliasesMem PSLIST_ENTRY ListEntry,
    _Inout_opt_ _Requires_lock_not_held_(*_Curr_) PKSPIN_LOCK Lock
    );
```

## -remarks

For more information about using this routine to implement a sequenced singly linked list, see <a href="/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists">Singly and Doubly Linked Lists</a>.

On Windows 2000, drivers must use the <b>-D_WIN2K_COMPAT_SLIST_USAGE</b> switch to successfully link code that uses <b>ExInterlockedPushEntrySList</b>.

The <b>ExInterlockedPushEntrySList</b> routine can be called at any IRQL. The storage for the <i>ListHead</i> parameter and the list entries must be resident at all IRQLs.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-initializeslisthead">ExInitializeSListHead</a>



<a href="/previous-versions/ff545402(v=vs.85)">ExInterlockedInsertTailList</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exinterlockedpopentryslist">ExInterlockedPopEntrySList</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exquerydepthslist">ExQueryDepthSList</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>