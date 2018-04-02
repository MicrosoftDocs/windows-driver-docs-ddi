---
UID: NF:wudfwdm.PopEntryList
title: PopEntryList function
author: windows-driver-content
description: The PopEntryList routine removes the first entry from a singly linked list of SINGLE_LIST_ENTRY structures.
old-location: kernel\popentrylist.htm
old-project: kernel
ms.assetid: b24ec573-4164-4016-a19d-574ebd75ec8f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PopEntryList, PopEntryList routine [Kernel-Mode Driver Architecture], k109_a5d1634c-e1ab-43ac-ab3f-d0993263f5bb.xml, kernel.popentrylist, wdm/PopEntryList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfwdm.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	PopEntryList
product: Windows
targetos: Windows
req.typenames: PO_FX_PERF_STATE_UNIT, *PPO_FX_PERF_STATE_UNIT
req.product: Windows 10 or later.
---

# PopEntryList function


## -description


The <b>PopEntryList</b> routine removes the first entry from a singly linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563799">SINGLE_LIST_ENTRY</a> structures.


## -syntax


````
PSINGLE_LIST_ENTRY PopEntryList(
  _Inout_ PSINGLE_LIST_ENTRY ListHead
);
````


## -parameters




### -param ListHead [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563799">SINGLE_LIST_ENTRY</a> structure that represents the head of the list. On return, <i>ListHead</i>-&gt;<b>Next</b> points to the beginning of the list with the first entry removed. 


## -returns



<b>PopEntryList</b> returns a pointer to the entry removed from the list, or <b>NULL</b> if the list is currently empty.




## -remarks



<b>PopEntryList</b> removes the first entry from the list by setting <i>ListHead</i>-&gt;<b>Next</b> to point to the second entry in the list.

For information about using this routine when implementing a singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>PopEntryList</b> can be running at any IRQL. If <b>PopEntryList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for <i>ListHead</i> and the list entries must be resident.




## -see-also

<a href="..\wudfwdm\nf-wudfwdm-pushentrylist.md">PushEntryList</a>



<a href="..\wdm\nf-wdm-exinterlockedpopentrylist.md">ExInterlockedPopEntryList</a>



 

 



