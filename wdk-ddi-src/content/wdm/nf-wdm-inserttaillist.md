---
UID: NF:wdm.InsertTailList
title: InsertTailList function (wdm.h)
description: The InsertTailList routine inserts an entry at the tail of a doubly linked list of LIST_ENTRY structures.
old-location: kernel\inserttaillist.htm
tech.root: kernel
ms.assetid: 9eb470c8-ee37-497e-982e-d32b4b9b7348
ms.date: 04/30/2018
keywords: ["InsertTailList function"]
ms.keywords: InsertTailList, InsertTailList routine [Kernel-Mode Driver Architecture], k109_8f31d6a6-89a0-440c-9397-2bef61a5878f.xml, kernel.inserttaillist, wdm/InsertTailList
f1_keywords:
 - "wdm/InsertTailList"
 - "InsertTailList"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- InsertTailList
targetos: Windows
req.typenames: 
---

# InsertTailList function


## -description


The <b>InsertTailList</b> routine inserts an entry at the tail of a doubly linked list of <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-list_entry">LIST_ENTRY</a> structures.


## -parameters




### -param ListHead 
[in, out]
Pointer to the <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-list_entry">LIST_ENTRY</a> structure that represents the head of the list.


### -param Entry 
[in, out]
Pointer to a <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-list_entry">LIST_ENTRY</a> structure that represents the entry to be inserted in the list.


## -remarks



<b>InsertTailList</b> updates <i>ListHead</i>-><b>Blink</b> to point to <i>Entry</i>. It updates <i>Entry</i>-><b>Blink</b> to point to the old last entry in the list, and sets <i>Entry</i>-><b>Flink</b> to <i>ListHead</i>. The <b>Flink</b> of the previous last entry is updated to point to <i>Entry</i> as well.

For information about using this routine when implementing a doubly linked list, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists">Singly and Doubly Linked Lists</a>.

Callers of <b>InsertTailList</b> can be running at any IRQL. If <b>InsertTailList</b> is called at IRQL >= DISPATCH_LEVEL, the storage for <i>ListHead</i> and the list entries must be resident.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545402">ExInterlockedInsertTailList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-initializelisthead">InitializeListHead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-insertheadlist">InsertHeadList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-islistempty">IsListEmpty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-removeheadlist">RemoveHeadList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-removetaillist">RemoveTailList</a>
 

 

