---
UID: NF:wdm.ExInterlockedFlushSList~r1
title: ExInterlockedFlushSList function (wdm.h)
description: The ExInterlockedFlushSList routine atomically removes all entries from a sequenced singly linked list.
old-location: kernel\exinterlockedflushslist.htm
tech.root: kernel
ms.date: 12/07/2021
keywords: ["ExInterlockedFlushSList macro"]
ms.keywords: ExInterlockedFlushSList, ExInterlockedFlushSList routine [Kernel-Mode Driver Architecture], k102_493935e2-44c7-471b-807f-ca6f110d8155.xml, kernel.exinterlockedflushslist, wdm/ExInterlockedFlushSList
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
 - ExInterlockedFlushSList
 - wdm/ExInterlockedFlushSList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExInterlockedFlushSList
---

# ExInterlockedFlushSList macro


## -description

The <b>ExInterlockedFlushSList</b> routine atomically removes all entries from a sequenced singly linked list.

## -syntax

```cpp
NTKERNELAPI
PSLIST_ENTRY
FASTCALL
ExInterlockedFlushSList (
    _Inout_ PSLIST_HEADER ListHead
    );
```

## -parameters

### -param ListHead [in, out]

A pointer to the <a href="/windows-hardware/drivers/kernel/eprocess">SLIST_HEADER</a> structure that serves as the header for the sequenced singly linked list.

## -returns

If there were entries on the specified list, **ExInterlockedFlushSList** returns a pointer to the first [**SLIST_ENTRY**](./ns-wdm-_slist_entry.md) structure that was an entry on the list; otherwise, it returns NULL.

## -remarks

<b>ExInterlockedFlushSList</b> does not delete the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_slist_entry">SLIST_ENTRY</a> structures that made up the list; it only sets the internal pointer of <i>ListHead</i> to the beginning of the list to <b>NULL</b>. The driver must free the entries explicitly.

The routine returns a pointer to the first <b>SLIST_ENTRY</b> structure that was on the list. The driver can use this pointer to iterate through the entries.

For more information about using this routine to implement a sequenced singly linked list, see <a href="/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists">Singly and Doubly Linked Lists</a>.

Callers of <b>ExInterlockedFlushSList</b> can be running at any IRQL. The storage for the <i>ListHead</i> parameter and the list entries must be resident at all IRQLs.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-initializeslisthead">ExInitializeSListHead</a>
