---
UID: NF:wdm.PushEntryList
title: PushEntryList function (wdm.h)
description: The PushEntryList routine inserts an entry at the beginning of a singly linked list of SINGLE_LIST_ENTRY structures.
old-location: kernel\pushentrylist.htm
tech.root: kernel
ms.assetid: 19f387d3-6c00-4c71-8114-61c53654613c
ms.date: 04/30/2018
ms.keywords: PushEntryList, PushEntryList routine [Kernel-Mode Driver Architecture], k109_17626baa-0fb7-4492-9e9c-a25b78b808fb.xml, kernel.pushentrylist, wdm/PushEntryList
ms.topic: function
f1_keywords:
 - "wdm/PushEntryList"
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
- PushEntryList
product:
- Windows
targetos: Windows
req.typenames: 
---

# PushEntryList function


## -description


The <b>PushEntryList</b> routine inserts an entry at the beginning of a singly linked list of <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_single_list_entry">SINGLE_LIST_ENTRY</a> structures.


## -parameters




### -param ListHead [in, out]

Pointer to the <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_single_list_entry">SINGLE_LIST_ENTRY</a> structure that serves as the list header.


### -param Entry [in, out]

Pointer to SINGLE_LIST_ENTRY structure that represents the entry to be inserted on the list.


## -returns



None




## -remarks



<b>PushEntryList</b> sets <i>ListHead</i>-><b>Next</b> to <i>Entry</i>, and <i>Entry</i>-><b>Next</b> to point to the old first entry of the list.

For information about using this routine when implementing a singly linked list, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists">Singly and Doubly Linked Lists</a>.

Callers of <b>PushEntryList</b> can be running at any IRQL. If <b>PushEntryList</b> is called at IRQL >= DISPATCH_LEVEL, the storage for <i>ListHead</i> and the list entries must be resident.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545418">ExInterlockedPushEntryList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-popentrylist">PopEntryList</a>
 

 

