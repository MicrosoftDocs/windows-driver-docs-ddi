---
UID: NF:wdm.RemoveTailList
title: RemoveTailList function (wdm.h)
description: The RemoveTailList routine removes an entry from the end of a doubly linked list of LIST_ENTRY structures.
old-location: kernel\removetaillist.htm
tech.root: kernel
ms.assetid: 67942bf7-28f6-4b2d-a880-9439afaf0bb2
ms.date: 04/30/2018
ms.keywords: RemoveTailList, RemoveTailList routine [Kernel-Mode Driver Architecture], k109_b9ce310f-ead1-46ee-a591-ae018f61f536.xml, kernel.removetaillist, wdm/RemoveTailList
ms.topic: function
f1_keywords:
 - "wdm/RemoveTailList"
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
req.irql: Any level (See Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- RemoveTailList
product:
- Windows
targetos: Windows
req.typenames: 
---

# RemoveTailList function


## -description


The <b>RemoveTailList</b> routine removes an entry from the end of a doubly linked list of <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_list_entry">LIST_ENTRY</a> structures.


## -parameters




### -param ListHead [in, out]

Pointer to the <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_list_entry">LIST_ENTRY</a> structure that serves as the list header.


## -returns



<b>RemoveTailList</b> returns a pointer to the entry that was at the tail of the list. If the list is empty, <b>RemoveTailList</b> returns <i>ListHead</i>. 




## -remarks



<b>RemoveTailList</b> removes the last entry from the list by setting <i>ListHead</i>-><b>Blink</b> to point to the second-to-last entry in the list. The routine sets the <b>Flink</b> member of the new first entry to <i>ListHead</i>. In the event the list is empty, this is effectively a no-op.

For information about using this routine when implementing a doubly linked list, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists">Singly and Doubly Linked Lists</a>.

Callers of <b>InsertHeadList</b> can be running at any IRQL. If <b>InsertHeadList</b> is called at IRQL >= DISPATCH_LEVEL, the storage for <i>ListHead</i> and the list entries must be resident.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-initializelisthead">InitializeListHead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-islistempty">IsListEmpty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-removeentrylist">RemoveEntryList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-removeheadlist">RemoveHeadList</a>
 

 

