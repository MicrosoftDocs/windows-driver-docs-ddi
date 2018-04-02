---
UID: NF:wudfwdm.RemoveHeadList
title: RemoveHeadList function
author: windows-driver-content
description: The RemoveHeadList routine removes an entry from the beginning of a doubly linked list of LIST_ENTRY structures.
old-location: kernel\removeheadlist.htm
old-project: kernel
ms.assetid: 8748451c-3e57-4acf-b1e6-b80fe7f461d8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RemoveHeadList, RemoveHeadList routine [Kernel-Mode Driver Architecture], k109_f16481a9-4fd3-4b81-9fd3-aa77b20f9873.xml, kernel.removeheadlist, wdm/RemoveHeadList
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
req.ddi-compliance: CancelSpinLock, CompleteRequest, DoubleCompletion, IoAllocateFree, IoReuseIrp, IrpProcessingComplete, MarkingInterlockedQueuedIrps, MarkingQueuedIrps, MarkIrpPending, MarkIrpPending2, PendedCompletedRequest, PendedCompletedRequest2, PendedCompletedRequest3, PendedCompletedRequestEx, RemoveLock, RemoveLockCheck, RemoveLockForward, RemoveLockForward2, RemoveLockForwardDeviceControl, RemoveLockForwardDeviceControl2, RemoveLockForwardDeviceControlInternal, RemoveLockForwardDeviceControlInternal2, RemoveLockForwardRead, RemoveLockForwardRead2, RemoveLockForwardWrite, RemoveLockForwardWrite2, RemoveLockMnRemove, RemoveLockMnSurpriseRemove, RemoveLockRelease2, RemoveLockReleaseCleanup, RemoveLockReleaseClose, RemoveLockReleaseCreate, RemoveLockReleaseDeviceControl, RemoveLockReleaseInternalDeviceControl, RemoveLockReleasePnp, RemoveLockReleasePower, RemoveLockReleaseRead, RemoveLockReleaseShutdown, RemoveLockReleaseSystemControl, RemoveLockReleaseWrite, InvalidReqAccessLocal, DoubleExFreePool, Init_NdisAllocateIoWorkItem
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
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
-	RemoveHeadList
product: Windows
targetos: Windows
req.typenames: PO_FX_PERF_STATE_UNIT, *PPO_FX_PERF_STATE_UNIT
req.product: Windows 10 or later.
---

# RemoveHeadList function


## -description


The <b>RemoveHeadList</b> routine removes an entry from the beginning of a doubly linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structures. 


## -syntax


````
PLIST_ENTRY RemoveHeadList(
  _Inout_ PLIST_ENTRY ListHead
);
````


## -parameters




### -param ListHead [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that serves as the list header.


## -returns



<b>RemoveHeadList</b> returns a pointer to the entry removed from the list. If the list is empty, <b>RemoveHeadList</b> returns <i>ListHead</i>. 




## -remarks



<b>RemoveHeadList</b> removes the first entry from the list by setting <i>ListHead</i>-&gt;<b>Flink</b> to point to the second entry in the list. The routine sets the <b>Blink</b> member of the second entry to <i>ListHead</i>. In the event the list is empty, this is effectively a no-op.

For information about using this routine when implementing a doubly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>RemoveHeadList</b> can be running at any IRQL. If <b>RemoveHeadList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for <i>ListHead</i> and the list entries must be resident.




## -see-also

<a href="..\wdm\nf-wdm-exinterlockedremoveheadlist.md">ExInterlockedRemoveHeadList</a>



<a href="..\wudfwdm\nf-wudfwdm-initializelisthead.md">InitializeListHead</a>



<a href="..\wudfwdm\nf-wudfwdm-removetaillist.md">RemoveTailList</a>



<a href="..\wudfwdm\nf-wudfwdm-removeentrylist.md">RemoveEntryList</a>



<a href="..\wudfwdm\nf-wudfwdm-islistempty.md">IsListEmpty</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RemoveHeadList routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

