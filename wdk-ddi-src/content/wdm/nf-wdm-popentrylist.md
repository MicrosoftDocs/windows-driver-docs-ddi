---
UID: NF:wdm.PopEntryList
title: PopEntryList function (wdm.h)
description: The PopEntryList routine removes the first entry from a singly linked list of SINGLE_LIST_ENTRY structures.
old-location: kernel\popentrylist.htm
tech.root: kernel
ms.assetid: b24ec573-4164-4016-a19d-574ebd75ec8f
ms.date: 04/30/2018
keywords: ["PopEntryList function"]
ms.keywords: PopEntryList, PopEntryList routine [Kernel-Mode Driver Architecture], k109_a5d1634c-e1ab-43ac-ab3f-d0993263f5bb.xml, kernel.popentrylist, wdm/PopEntryList
f1_keywords:
 - "wdm/PopEntryList"
 - "PopEntryList"
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
- PopEntryList
targetos: Windows
req.typenames: 
---

# PopEntryList function


## -description


The <b>PopEntryList</b> routine removes the first entry from a singly linked list of <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_single_list_entry">SINGLE_LIST_ENTRY</a> structures.


## -parameters




### -param ListHead 
[in, out]
Pointer to the <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_single_list_entry">SINGLE_LIST_ENTRY</a> structure that represents the head of the list. On return, <i>ListHead</i>-><b>Next</b> points to the beginning of the list with the first entry removed. 


## -returns



<b>PopEntryList</b> returns a pointer to the entry removed from the list, or <b>NULL</b> if the list is currently empty.




## -remarks



<b>PopEntryList</b> removes the first entry from the list by setting <i>ListHead</i>-><b>Next</b> to point to the second entry in the list.

For information about using this routine when implementing a singly linked list, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists">Singly and Doubly Linked Lists</a>.

Callers of <b>PopEntryList</b> can be running at any IRQL. If <b>PopEntryList</b> is called at IRQL >= DISPATCH_LEVEL, the storage for <i>ListHead</i> and the list entries must be resident.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545408">ExInterlockedPopEntryList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pushentrylist">PushEntryList</a>
 

 

