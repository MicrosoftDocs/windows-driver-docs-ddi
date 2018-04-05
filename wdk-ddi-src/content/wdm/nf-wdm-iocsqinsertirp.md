---
UID: NF:wdm.IoCsqInsertIrp
title: IoCsqInsertIrp function
author: windows-driver-content
description: The IoCsqInsertIrp routine inserts an IRP in the driver's cancel-safe IRP queue.
old-location: kernel\iocsqinsertirp.htm
old-project: kernel
ms.assetid: ddfc0241-eab0-462b-8e1b-32bb9bcb3671
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoCsqInsertIrp, IoCsqInsertIrp routine [Kernel-Mode Driver Architecture], k104_cecd79a7-3c42-45a2-99f7-54ca2a3e0358.xml, kernel.iocsqinsertirp, wdm/IoCsqInsertIrp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows. Drivers that must also work in Windows 2000 and Windows 98/Me can instead link to Csq.lib to use the routine.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IoAllocateFree, IoReuseIrp, IrpCancelField, RemoveLockCheck, RemoveLockForward, RemoveLockForward2, RemoveLockForwardDeviceControl, RemoveLockForwardDeviceControl2, RemoveLockForwardDeviceControlInternal, RemoveLockForwardDeviceControlInternal2, RemoveLockForwardRead, RemoveLockForwardRead2, RemoveLockForwardWrite, RemoveLockForwardWrite2, RemoveLockReleaseCleanup, RemoveLockReleaseClose, RemoveLockReleaseCreate, RemoveLockReleaseDeviceControl, RemoveLockReleaseInternalDeviceControl, RemoveLockReleasePower, RemoveLockReleaseRead, RemoveLockReleaseShutdown, RemoveLockReleaseSystemControl, RemoveLockReleaseWrite
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoCsqInsertIrp
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoCsqInsertIrp function


## -description


The <b>IoCsqInsertIrp</b> routine inserts an IRP in the driver's cancel-safe IRP queue.


## -parameters




### -param Csq [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure for the driver's cancel-safe IRP queue. This structure must have been initialized by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549054">IoCsqInitialize</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549060">IoCsqInitializeEx</a>. 


### -param Irp [in, out]

Pointer to the IRP to be queued.


### -param Context [out, optional]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550567">IO_CSQ_IRP_CONTEXT</a> structure. <b>IoCsqInsertIrp</b> initializes this structure with context information for the inserted IRP. The driver passes this value to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549070">IoCsqRemoveIrp</a> to delete the IRP from the queue. <i>Context</i> can be <b>NULL</b> if the driver will not use <b>IoCsqRemoveIrp</b> to remove this IRP from the queue. 


## -returns



None




## -remarks



<b>IoCsqInsertIrp</b> uses the queue's dispatch routines to insert the IRP. The <b>IoCsqInsertIrp</b> routine:

<ol>
<li>
Calls the queue's <a href="https://msdn.microsoft.com/library/windows/hardware/ff542934">CsqAcquireLock</a> routine to lock the queue.

</li>
<li>
Calls the queue's <a href="https://msdn.microsoft.com/library/windows/hardware/ff542947">CsqInsertIrp</a> routine to insert the IRP.

</li>
<li>
Marks the IRP as pending.

</li>
<li>
Calls the queue's <a href="https://msdn.microsoft.com/library/windows/hardware/ff542965">CsqReleaseLock</a> routine to unlock the queue.

</li>
</ol>
If the IRP to be inserted has already been canceled, <b>IoCsqInsertIrp</b> does not attempt to insert the IRP into the queue.

Drivers can also use <a href="https://msdn.microsoft.com/library/windows/hardware/ff549067">IoCsqInsertIrpEx</a> to insert an IRP into the queue. For a queue that is specified by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549060">IoCsqInitializeEx</a>, <b>IoCsqInsertIrpEx</b> provides additional capabilities. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.

Note that the <b>IoCsq<i>Xxx</i></b> routines use the <b>DriverContext</b>[3] member of the IRP to hold IRP context information. Drivers that use these routines to queue IRPs must leave that member unused.

Callers of <b>IoCsqInsertIrp</b> must be running at an IRQL &lt;= DISPATCH_LEVEL. The driver's callback routines must work correctly at that IRQL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542934">CsqAcquireLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542940">CsqCompleteCanceledIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542947">CsqInsertIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542956">CsqInsertIrpEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542959">CsqPeekNextIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542965">CsqReleaseLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542968">CsqRemoveIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550567">IO_CSQ_IRP_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549054">IoCsqInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549060">IoCsqInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549067">IoCsqInsertIrpEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549070">IoCsqRemoveIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549072">IoCsqRemoveNextIrp</a>
 

 

