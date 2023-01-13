---
UID: NF:wdm.AppendTailList
title: AppendTailList function (wdm.h)
description: The AppendTailList routine appends a doubly linked list of LIST_ENTRY structures to the tail of another doubly linked list of LIST_ENTRY structures.
tech.root: kernel
ms.date: 01/10/2023
keywords: ["AppendTailList function"]
ms.keywords: AppendTailList, AppendTailList routine [Kernel-Mode Driver Architecture], kernel.appendtaillist, wdm/AppendTailList
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
req.target-type: Desktop
req.target-min-winverclnt:
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
req.lib: 
req.dll: 
req.irql: Any level (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - AppendTailList
 - wdm/AppendTailList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - AppendTailList
---

## -description

The **AppendTailList** routine appends a doubly linked list of [**LIST_ENTRY**](/windows/win32/api/ntdef/ns-ntdef-list_entry) structures to the tail of another doubly linked list of **LIST_ENTRY** structures.

## -parameters

### -param ListHead [in, out]

A pointer to the head of the list to which the list pointed to by *ListToAppend* is to be appended. This parameter must be a valid, non-NULL pointer to the [LIST_ENTRY](/windows/win32/api/ntdef/ns-ntdef-list_entry) structure that is the head of a list. This list can be empty.

### -param ListToAppend [in, out]

A pointer to the first entry in the list to append to the list pointed to by *ListHead*. This parameter must be a valid, non-NULL pointer to the [LIST_ENTRY](/windows/win32/api/ntdef/ns-ntdef-list_entry) structure that is the first entry in a headless list. For more information, see Remarks.

## -remarks

This routine constructs a list that contains all the combined entries from the input *ListHead* and *ListToAppend* lists. When the routine returns, the [LIST_ENTRY](/windows/win32/api/ntdef/ns-ntdef-list_entry) structure pointed to by the *ListHead* parameter is the head of the resulting combined list. The **LIST_ENTRY** structure pointed to by the *ListToAppend* parameter is an entry in the resulting combined list.

The caller sets the *ListToAppend* parameter to point to the first entry in the list to be appended. In this regard, *AppendTailList* does not conform to the convention followed by the other doubly linked list routines that use the **LIST_ENTRY** structure. In these other routines, a parameter that represents a list points to the list head instead of to the first entry in the list. If your driver code uses a list head to represent the list to be appended, the list head must be removed from this list before the list is passed as the *ListToAppend* parameter to **AppendTailList**. For a code example that shows how to remove this list head, see Examples.

**AppendTailList** can be used to insert a single entry at the tail of a list, but the **Flink** and **Blink** members of the **LIST_ENTRY** structure pointed to by *ListToAppend* must first be initialized—typically, by calling the [InitializeListHead](/windows-hardware/drivers/ddi/wdm/nf-wdm-initializelisthead) routine. In contrast, the [InsertTailList](/windows-hardware/drivers/ddi/wdm/nf-wdm-inserttaillist) routine does not require the **Flink** and **Blink** members of the **LIST_ENTRY** structure pointed to by the *Entry* parameter to be initialized before the **InsertTailList** call. For this reason, **InsertTailList** might be more convenient to use to insert a single entry at the tail of a list.

A driver can access the **Flink** and **Blink** members of a **LIST_ENTRY**, but the members must only be updated by the system routines supplied for this purpose.

For information about using this routine when implementing a doubly linked list, see [Singly and Doubly Linked Lists](/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists).

Callers of **AppendTailList** can be running at any IRQL. If **AppendTailList** is called at IRQL >= DISPATCH_LEVEL, the storage for the list entries must be memory-resident.

### Examples

The following code example shows how to write a function named `MyAppendTailList` that is similar to **AppendTailList**, but that treats the *ListToAppend* parameter as a pointer to a list head instead of as a pointer to the first entry in a (headless) list. Unlike **AppendTailList**, the `MyAppendTailList` function avoids including the **LIST_ENTRY** structure pointed to by the *ListToAppend* parameter in the entries that are appended to the list pointed to by the *ListHead* parameter.

```cpp
VOID MyAppendTailList(
    _Inout_  PLIST_ENTRY ListHead,
    _Inout_  PLIST_ENTRY ListToAppend
    )
{
    PLIST_ENTRY entry = ListToAppend->Flink;

    if (!IsListEmpty(ListToAppend))
    {
        RemoveEntryList(ListToAppend);
        InitializeListHead(ListToAppend);
        AppendTailList(ListHead, entry);
    }
}
```

The `MyAppendTailList` function in this code example treats both the *ListHead* and *ListToAppend* parameters as pointers to list heads. When this function returns, the list pointed to by *ListToAppend* is empty; that is, it consists of a list head that has no associated list entries. All of the entries that were initially in this list have been appended to the list pointed to by *ListHead*.

## -see-also

[InitializeListHead](/windows-hardware/drivers/ddi/wdm/nf-wdm-initializelisthead)

[InsertTailList](/windows-hardware/drivers/ddi/wdm/nf-wdm-inserttaillist)

[**LIST_ENTRY**](/windows/win32/api/ntdef/ns-ntdef-list_entry)

[RemoveEntryList](/windows-hardware/drivers/ddi/wdm/nf-wdm-removeentrylist)
