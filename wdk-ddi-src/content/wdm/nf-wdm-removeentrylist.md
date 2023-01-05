---
UID: NF:wdm.RemoveEntryList
title: RemoveEntryList function (wdm.h)
description: The RemoveEntryList routine removes an entry from a doubly linked list of LIST_ENTRY structures.
tech.root: kernel
ms.date: 12/13/2022
keywords: ["RemoveEntryList function"]
ms.keywords: RemoveEntryList, RemoveEntryList routine [Kernel-Mode Driver Architecture], k109_138ddf01-d13f-4e36-9b66-c2e58914c170.xml, kernel.removeentrylist, wdm/RemoveEntryList
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
req.target-type: Desktop
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: DoubleExFreePool
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RemoveEntryList
 - wdm/RemoveEntryList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - RemoveEntryList
---

# RemoveEntryList function

## -description

The **RemoveEntryList** routine removes an entry from a doubly linked list of [LIST_ENTRY](/windows/win32/api/ntdef/ns-ntdef-list_entry) structures.

## -parameters

### -param Entry [in]

Pointer to the [LIST_ENTRY](/windows/win32/api/ntdef/ns-ntdef-list_entry) structure that represents the entry to be removed.

## -returns

**RemoveEntryList** returns **TRUE** if, after removal of the designated entry, the list is empty. Otherwise, the routine returns **FALSE** to indicate that the resulting list still contains one or more entries. For information, see the **Remarks** section below.

## -remarks

**RemoveEntryList** removes the entry by setting the **Flink** member of the entry before *Entry* to point to the entry after *Entry*, and the **Blink** member of the entry after *Entry* to point to the entry before *Entry*.

The return value can be used to detect when the last entry is removed from the list. An empty list consists of a list head only and no list entries.

Typically, *Entry* points to an entry in a list and not to the list head. However, *Entry* can point to a list head, in which case the routine removes the list head from the list to produce a headless list. When **RemoveEntryList** is used in this way, the return value should typically be ignored. To determine whether a list is empty, use the [IsListEmpty](/windows-hardware/drivers/ddi/wdm/nf-wdm-islistempty) routine.

For information about using this routine when implementing a doubly linked list, see [Singly and Doubly Linked Lists](/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists).

Callers of **RemoveEntryList** can be running at any IRQL. If **RemoveEntryList** is called at IRQL >= DISPATCH_LEVEL, the storage for the list entries must be resident.

## -see-also

[InitializeListHead](/windows-hardware/drivers/ddi/wdm/nf-wdm-initializelisthead)

[IsListEmpty](/windows-hardware/drivers/ddi/wdm/nf-wdm-islistempty)

[RemoveHeadList](/windows-hardware/drivers/ddi/wdm/nf-wdm-removeheadlist)

[RemoveTailList](/windows-hardware/drivers/ddi/wdm/nf-wdm-removetaillist)
