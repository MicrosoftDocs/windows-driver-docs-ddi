---
UID: NF:wudfwdm.InsertHeadList
title: InsertHeadList function
author: windows-driver-content
description: The InsertHeadList routine inserts an entry at the head of a doubly linked list of LIST_ENTRY structures.
old-location: kernel\insertheadlist.htm
tech.root: kernel
ms.assetid: c3ad9d93-93e1-406b-9a58-26dcbf428b50
ms.date: 04/30/2018
ms.keywords: InsertHeadList, InsertHeadList routine [Kernel-Mode Driver Architecture], k109_dde56187-8543-45cc-97fd-3fde2475e428.xml, kernel.insertheadlist, wdm/InsertHeadList
ms.topic: function
req.header: wudfwdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IoAllocateFree, IoReuseIrp, MarkingQueuedIrps, RemoveLockCheck, RemoveLockForward, RemoveLockForward2, RemoveLockForwardDeviceControl, RemoveLockForwardDeviceControl2, RemoveLockForwardDeviceControlInternal, RemoveLockForwardDeviceControlInternal2, RemoveLockForwardRead, RemoveLockForwardRead2, RemoveLockForwardWrite, RemoveLockForwardWrite2, RemoveLockRelease2, RemoveLockReleaseCleanup, RemoveLockReleaseClose, RemoveLockReleaseCreate, RemoveLockReleaseDeviceControl, RemoveLockReleaseInternalDeviceControl, RemoveLockReleasePower, RemoveLockReleaseRead, RemoveLockReleaseShutdown, RemoveLockReleaseSystemControl, RemoveLockReleaseWrite
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
-	InsertHeadList
product:
- Windows
targetos: Windows
req.typenames: 
---

# InsertHeadList function


## -description


The <b>InsertHeadList</b> routine inserts an entry at the head of a doubly linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structures.


## -parameters




### -param ListHead [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that represents the head of the list.


### -param Entry [in, out]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that represents the entry to be inserted into the list. 


## -returns



None




## -remarks



<b>InsertHeadList</b> updates <i>ListHead</i>-&gt;<b>Flink</b> to point to <i>Entry</i>. It updates <i>Entry</i>-&gt;<b>Flink</b> to point to the old first entry in the list, and sets <i>Entry</i>-&gt;<b>Blink</b> to <i>ListHead</i>. The <b>Blink</b> field of the original first entry is also updated to point to <i>Entry</i>.

For information about using this routine when implementing a doubly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>InsertHeadList</b> can be running at any IRQL. If <b>InsertHeadList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for <i>ListHead</i> and the list entries must be resident.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545397">ExInterlockedInsertHeadList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547799">InitializeListHead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547823">InsertTailList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551789">IsListEmpty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561032">RemoveHeadList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561036">RemoveTailList</a>
 

 



