---
UID: NF:wdm.ExInterlockedPopEntryList
title: ExInterlockedPopEntryList function (wdm.h)
description: The ExInterlockedPopEntryList routine atomically removes an entry from the beginning of a singly linked list of SINGLE_LIST_ENTRY structures.
old-location: kernel\exinterlockedpopentrylist.htm
tech.root: kernel
ms.assetid: 339e688f-64ec-402f-bd28-9fa487acb984
ms.date: 04/30/2018
keywords: ["ExInterlockedPopEntryList function"]
ms.keywords: ExInterlockedPopEntryList, ExInterlockedPopEntryList routine [Kernel-Mode Driver Architecture], k102_4673c5a1-a650-48c3-934f-c35c202277cc.xml, kernel.exinterlockedpopentrylist, wdm/ExInterlockedPopEntryList
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
 - ExInterlockedPopEntryList
 - wdm/ExInterlockedPopEntryList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExInterlockedPopEntryList
---

# ExInterlockedPopEntryList function


## -description

The <b>ExInterlockedPopEntryList</b> routine atomically removes an entry from the beginning of a singly linked list of <a href="/windows/win32/api/ntdef/ns-ntdef-single_list_entry">SINGLE_LIST_ENTRY</a> structures.

## -parameters

### -param ListHead 

[in, out]
A pointer to the <a href="/windows/win32/api/ntdef/ns-ntdef-single_list_entry">SINGLE_LIST_ENTRY</a> structure that serves as the list header.

### -param Lock 

[in, out]
A pointer to a <b>KSPIN_LOCK</b> structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>. You must use this spin lock only with the <b>ExInterlocked<i>Xxx</i>List</b> routines.

## -returns

<b>ExInterlockedPopEntryList</b> returns a pointer to the <a href="/windows/win32/api/ntdef/ns-ntdef-single_list_entry">SINGLE_LIST_ENTRY</a> structure removed from the list. If the list was empty, the routine returns <b>NULL</b>.

## -remarks

<b>ExInterlockedPopEntryList</b> performs the same operation as <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-popentrylist">PopEntryList</a>, but atomically. Do not mix atomic and non-atomic calls on the same list.

For more information about using this routine to implement a singly linked list, see <a href="/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists">Singly and Doubly Linked Lists</a>.

The <b>ExInterlockedPopEntryList</b> routine can be called at any IRQL. The storage for the <i>ListHead</i> parameter must be resident at all IRQLs.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-initializeslisthead">ExInitializeSListHead</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exinterlockedpopentryslist">ExInterlockedPopEntrySList</a>



<a href="/previous-versions/ff545418(v=vs.85)">ExInterlockedPushEntryList</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-popentrylist">PopEntryList</a>