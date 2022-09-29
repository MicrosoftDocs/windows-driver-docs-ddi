---
UID: NF:storport.StorPortInterlockedInsertHeadList
title: StorPortInterlockedInsertHeadList function (storport.h)
description: The StorPortInterlockedInsertHeadList routine atomically inserts an entry at the beginning of a doubly linked list of STOR_LIST_ENTRY structures.
old-location: storage\storportinterlockedinsertheadlist.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortInterlockedInsertHeadList function"]
ms.keywords: StorPortInterlockedInsertHeadList, StorPortInterlockedInsertHeadList routine [Storage Devices], storage.storportinterlockedinsertheadlist, storport/StorPortInterlockedInsertHeadList
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.typenames: 
f1_keywords:
 - StorPortInterlockedInsertHeadList
 - storport/StorPortInterlockedInsertHeadList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortInterlockedInsertHeadList
---

# StorPortInterlockedInsertHeadList function

## -description

The StorPortInterlockedInsertHeadList routine atomically inserts an entry at the beginning of a doubly linked list of [**STOR_LIST_ENTRY**](ns-storport-_stor_list_entry.md) structures.

## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).

### -param ListHead [in, out]

Pointer to the [**STOR_LIST_ENTRY**](ns-storport-_stor_list_entry.md) structure that represents the head of the list.

### -param ListEntry [in, out]

Pointer to a [**STOR_LIST_ENTRY**](ns-storport-_stor_list_entry.md) structure that represents the entry to be inserted into the list.

### -param Result [in, out]

Pointer to a [**STOR_LIST_ENTRY**](ns-storport-_stor_list_entry.md) structure that represents the first entry of the list before the new entry was inserted.

### -param Lock [in, out]

A pointer to a **STOR_KSPIN_LOCK** structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling [**StorPortInitializeSpinLock**](nf-storport-storportinitializespinlock.md).

You must use this spin lock only with the **StorPortInterlocked*Xxx*List** routines.

## -returns

**StorPortInterlockedInsertHeadList** returns a status code such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_NOT_IMPLEMENTED   | This function is not implemented on the active operating system. |
| STOR_STATUS_SUCCESS           | The list items were removed successfully or the list is already empty. |
| STOR_STATUS_INVALID_PARAMETER | A pointer in **ListHead** or **Result** is **NULL**. |

## -see-also

[**InitializeListHead**](../wdm/nf-wdm-initializelisthead.md)

[**InsertHeadList**](../wdm/nf-wdm-insertheadlist.md)

[**StorPortInitializeSpinLock**](nf-storport-storportinitializespinlock.md)

[**StorPortInterlockedInsertTailList**](nf-storport-storportinterlockedinserttaillist.md)

[**StorPortInterlockedRemoveHeadList**](nf-storport-storportinterlockedremoveheadlist.md)
