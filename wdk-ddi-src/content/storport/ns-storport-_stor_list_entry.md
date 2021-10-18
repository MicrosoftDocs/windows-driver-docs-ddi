---
UID: NS:storport._STOR_LIST_ENTRY
title: STOR_LIST_ENTRY (storport.h)
description: A STOR_LIST_ENTRY structure describes an entry in a doubly linked list or serves as the header for such a list.
old-location: storage\stor_list_entry.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["STOR_LIST_ENTRY structure"]
ms.keywords: "*PSTOR_LIST_ENTRY, PSTOR_LIST_ENTRY, PSTOR_LIST_ENTRY structure pointer [Storage Devices], STOR_LIST_ENTRY, STOR_LIST_ENTRY structure [Storage Devices], _STOR_LIST_ENTRY, storage.stor_list_entry, storport/PSTOR_LIST_ENTRY, storport/STOR_LIST_ENTRY"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
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
req.irql: 
targetos: Windows
req.typenames: STOR_LIST_ENTRY, *PSTOR_LIST_ENTRY
f1_keywords:
 - _STOR_LIST_ENTRY
 - storport/_STOR_LIST_ENTRY
 - PSTOR_LIST_ENTRY
 - storport/PSTOR_LIST_ENTRY
 - STOR_LIST_ENTRY
 - storport/STOR_LIST_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_LIST_ENTRY
 - PSTOR_LIST_ENTRY
 - STOR_LIST_ENTRY
---

# STOR_LIST_ENTRY structure

## -description

A **STOR_LIST_ENTRY** structure describes an entry in a doubly linked list or serves as the header for such a list.

## -struct-fields

### -field Flink

For a **LIST_ENTRY** structure that serves as a list entry, the **Flink** member points to the next entry in the list or to the list header if there is no next entry in the list.

For a **LIST_ENTRY** structure that serves as the list header, the **Flink** member points to the first entry in the list or to the LIST_ENTRY structure itself if the list is empty.

### -field Blink

For a **LIST_ENTRY** structure that serves as a list entry, the **Blink** member points to the previous entry in the list or to the list header if there is no previous entry in the list.

For a **LIST_ENTRY** structure that serves as the list header, the **Blink** member points to the last entry in the list or to the **LIST_ENTRY** structure itself if the list is empty.

## -remarks

A **STOR_LIST_ENTRY** structure that describes the list head must have been initialized by calling [**StorPortInitializeListHead**](nf-storport-storportinitializelisthead.md).

A driver can access the **Flink** or **Blink** members of a **STOR_LIST_ENTRY**, but the members must only be updated by the system routines supplied for this purpose.

For more information about how to use **STOR_LIST_ENTRY** structures to implement a doubly linked list, see [Singly and Doubly Linked Lists](/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists).

## -see-also

[**InitializeListHead**](../wdm/nf-wdm-initializelisthead.md)

[**InsertHeadList**](../wdm/nf-wdm-insertheadlist.md)

[**InsertTailList**](../wdm/nf-wdm-inserttaillist.md)

[**IsListEmpty**](../wdm/nf-wdm-islistempty.md)

[**RemoveEntryList**](../wdm/nf-wdm-removeentrylist.md)

[**RemoveHeadList**](../wdm/nf-wdm-removeheadlist.md)

[**RemoveTailList**](../wdm/nf-wdm-removetaillist.md)

[**StorPortInterlockedInsertHeadList**](nf-storport-storportinterlockedinsertheadlist.md)

[**StorPortInterlockedInsertTailList**](nf-storport-storportinterlockedinserttaillist.md)

[**StorPortInterlockedRemoveHeadList**](nf-storport-storportinterlockedremoveheadlist.md)
