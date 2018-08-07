---
UID: NF:wudfwdm.RemoveEntryList
title: RemoveEntryList function
author: windows-driver-content
description: The RemoveEntryList routine removes an entry from a doubly linked list of LIST_ENTRY structures.
old-location: kernel\removeentrylist.htm
tech.root: kernel
ms.assetid: 84c3937f-8042-4b15-b5bb-884d14a97a8c
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RemoveEntryList, RemoveEntryList routine [Kernel-Mode Driver Architecture], k109_138ddf01-d13f-4e36-9b66-c2e58914c170.xml, kernel.removeentrylist, wdm/RemoveEntryList
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
req.ddi-compliance: DoubleExFreePool
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	RemoveEntryList
product:
- Windows
targetos: Windows
req.typenames: 
---

# RemoveEntryList function


## -description


The <b>RemoveEntryList</b> routine removes an entry from a doubly linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structures.


## -parameters




### -param Entry [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that represents the entry to be removed.


## -returns



<b>RemoveEntryList</b> returns <b>TRUE</b> if, after removal of the designated entry, the list is empty. Otherwise, the routine returns <b>FALSE</b> to indicate that the resulting list still contains one or more entries. For information, see Remarks.

<div class="alert"><b>Note</b>  Before Microsoft Windows Server 2003, <b>RemoveEntryList</b> was defined to return VOID, not BOOLEAN.</div>
<div> </div>



## -remarks



<b>RemoveEntryList</b> removes the entry by setting the <b>Flink</b> member of the entry before <i>Entry</i> to point to the entry after <i>Entry</i>, and the <b>Blink</b> member of the entry after <i>Entry</i> to point to the entry before <i>Entry</i>.

The return value can be used to detect when the last entry is removed from the list. An empty list consists of a list head only and no list entries.

<div class="alert"><b>Note</b>  Typically, <i>Entry</i> points to an entry in a list and not to the list head. However, <i>Entry</i> can point to a list head, in which case the routine removes the list head from the list to produce a headless list. When <b>RemoveEntryList</b> is used in this way, the return value should typically be ignored. To determine whether a list is empty, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551789">IsListEmpty</a> routine.</div>
<div> </div>
For information about using this routine when implementing a doubly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

In Windows XP and Windows 2000, <b>RemoveEntryList</b> did not return a value. Starting with Windows Server 2003, <b>RemoveEntryList</b> returns a BOOLEAN value.

Callers of <b>RemoveEntryList</b> can be running at any IRQL. If <b>RemoveEntryList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for the list entries must be resident.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547799">InitializeListHead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551789">IsListEmpty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561032">RemoveHeadList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561036">RemoveTailList</a>
 

 



