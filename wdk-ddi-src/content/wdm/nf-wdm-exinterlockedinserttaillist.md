---
UID: NF:wdm.ExInterlockedInsertTailList
title: ExInterlockedInsertTailList function (wdm.h)
description: The ExInterlockedInsertTailList routine atomically inserts an entry at the end of a doubly linked list of LIST_ENTRY structures.
old-location: kernel\exinterlockedinserttaillist.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExInterlockedInsertTailList function"]
ms.keywords: ExInterlockedInsertTailList, ExInterlockedInsertTailList routine [Kernel-Mode Driver Architecture], k102_a6d47e7b-63d2-48e9-9f6a-99f733194c1b.xml, kernel.exinterlockedinserttaillist, wdm/ExInterlockedInsertTailList
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IoAllocateFree, IoReuseIrp, MarkingInterlockedQueuedIrps, RemoveLockCheck, RemoveLockForward, RemoveLockForward2, RemoveLockForwardDeviceControl, RemoveLockForwardDeviceControl2, RemoveLockForwardDeviceControlInternal, RemoveLockForwardDeviceControlInternal2, RemoveLockForwardRead, RemoveLockForwardRead2, RemoveLockForwardWrite, RemoveLockForwardWrite2, RemoveLockRelease2, RemoveLockReleaseCleanup, RemoveLockReleaseClose, RemoveLockReleaseCreate, RemoveLockReleaseDeviceControl, RemoveLockReleaseInternalDeviceControl, RemoveLockReleasePower, RemoveLockReleaseRead, RemoveLockReleaseShutdown, RemoveLockReleaseSystemControl, RemoveLockReleaseWrite
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
 - ExInterlockedInsertTailList
 - wdm/ExInterlockedInsertTailList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExInterlockedInsertTailList
---

# ExInterlockedInsertTailList function


## -description

The <b>ExInterlockedInsertTailList</b> routine atomically inserts an entry at the end of a doubly linked list of <a href="/windows/win32/api/ntdef/ns-ntdef-list_entry">LIST_ENTRY</a> structures.

## -parameters

### -param ListHead 

[in, out]
A pointer to the <a href="/windows/win32/api/ntdef/ns-ntdef-list_entry">LIST_ENTRY</a> structure that serves as the list header.

### -param ListEntry 

[in, out]
A pointer to the <a href="/windows/win32/api/ntdef/ns-ntdef-list_entry">LIST_ENTRY</a> structure that represents the entry to be inserted into the list.

### -param Lock 

[in, out]
A pointer to a <b>KSPIN_LOCK</b> structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>. You must use this spin lock only with the <b>ExInterlocked<i>Xxx</i>List</b> routines.

## -returns

<b>ExInterlockedInsertTailList</b> returns a pointer to the last entry of the list <u>before</u> the new entry was inserted. If the list was empty, the routine returns <b>NULL</b>.

## -remarks

<b>ExInterlockedInsertTailList</b> performs the same operation as <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-inserttaillist">InsertTailList</a>, but atomically. Do not mix atomic and non-atomic calls on the same list.

For more information about using this routine to implement a doubly linked list, see <a href="/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists">Singly and Doubly Linked Lists</a>.

The <b>ExInterlockedInsertTailList</b> routine can be called at any IRQL. The storage for the <i>ListHead</i> parameter and the list entries must be resident at all IRQLs.

## -see-also

<a href="/previous-versions/ff545397(v=vs.85)">ExInterlockedInsertHeadList</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-initializelisthead">InitializeListHead</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-inserttaillist">InsertTailList</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>
