---
UID: NF:wdm.InitializeListHead
title: InitializeListHead function (wdm.h)
description: The InitializeListHead routine initializes a LIST_ENTRY structure that represents the head of a doubly linked list.
old-location: kernel\initializelisthead.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["InitializeListHead function"]
ms.keywords: InitializeListHead, InitializeListHead routine [Kernel-Mode Driver Architecture], k109_2e5e02a0-26d3-4c8a-b712-ee3d515b8a23.xml, kernel.initializelisthead, wdm/InitializeListHead
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
 - InitializeListHead
 - wdm/InitializeListHead
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - InitializeListHead
---

# InitializeListHead function


## -description

The <b>InitializeListHead</b> routine initializes a <a href="/windows/win32/api/ntdef/ns-ntdef-list_entry">LIST_ENTRY</a> structure that represents the head of a doubly linked list.

## -parameters

### -param ListHead 

[out]
Pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-list_entry">LIST_ENTRY</a> structure that serves as the list header.

## -remarks

The <b>InitializeListHead</b> routine sets the <b>Flink</b> and <b>Blink</b> members of <i>ListHead</i> to point to <i>ListHead</i>.

For information about using this routine when implementing a doubly linked list, see <a href="/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists">Singly and Doubly Linked Lists</a>.

Callers of <b>InitializeListHead</b> can be running at any IRQL. If <b>InitializeListHead</b> is called at IRQL >= DISPATCH_LEVEL the storage for <i>ListHead</i> must be resident.

## -see-also

<a href="/previous-versions/ff545397(v=vs.85)">ExInterlockedInsertHeadList</a>



<a href="/previous-versions/ff545402(v=vs.85)">ExInterlockedInsertTailList</a>



<a href="/previous-versions/ff545408(v=vs.85)">ExInterlockedPopEntryList</a>



<a href="/previous-versions/ff545418(v=vs.85)">ExInterlockedPushEntryList</a>



<a href="/previous-versions/ff545427(v=vs.85)">ExInterlockedRemoveHeadList</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-insertheadlist">InsertHeadList</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-inserttaillist">InsertTailList</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-islistempty">IsListEmpty</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-popentrylist">PopEntryList</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pushentrylist">PushEntryList</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-removeentrylist">RemoveEntryList</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-removeheadlist">RemoveHeadList</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-removetaillist">RemoveTailList</a>
