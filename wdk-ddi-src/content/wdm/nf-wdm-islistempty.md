---
UID: NF:wdm.IsListEmpty
title: IsListEmpty function (wdm.h)
description: The IsListEmpty routine indicates whether a doubly linked list of LIST_ENTRY structures is empty.
old-location: kernel\islistempty.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IsListEmpty function"]
ms.keywords: IsListEmpty, IsListEmpty routine [Kernel-Mode Driver Architecture], k109_26969818-30d0-4e01-965d-e0ee6891fdd5.xml, kernel.islistempty, wdm/IsListEmpty
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - IsListEmpty
 - wdm/IsListEmpty
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - IsListEmpty
---

# IsListEmpty function


## -description

The <b>IsListEmpty</b> routine indicates whether a doubly linked list of <a href="/windows/win32/api/ntdef/ns-ntdef-list_entry">LIST_ENTRY</a> structures is empty.

## -parameters

### -param ListHead 

[in]
Pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-list_entry">LIST_ENTRY</a> structure that represents the head of the list.

## -returns

<b>IsListEmpty</b> returns <b>TRUE</b> if there are currently no entries in the list and <b>FALSE</b> otherwise.

## -remarks

<b>IsListEmpty</b> returns <b>TRUE</b> if <i>ListHead</i>-><b>Flink</b> refers back to <i>ListHead</i>.

For information about using this routine when implementing a doubly linked list, see <a href="/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists">Singly and Doubly Linked Lists</a>.

Callers of <b>IsListEmpty</b> can be running at any IRQL. If <b>IsListEmpty</b> is called at IRQL >= DISPATCH_LEVEL, the storage for <i>ListHead</i> must be resident.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-initializelisthead">InitializeListHead</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-removeentrylist">RemoveEntryList</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-removeheadlist">RemoveHeadList</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-removetaillist">RemoveTailList</a>
