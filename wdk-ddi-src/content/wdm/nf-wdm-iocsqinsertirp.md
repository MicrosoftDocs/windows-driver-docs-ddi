---
UID: NF:wdm.IoCsqInsertIrp
title: IoCsqInsertIrp function (wdm.h)
description: The IoCsqInsertIrp routine inserts an IRP in the driver's cancel-safe IRP queue.
old-location: kernel\iocsqinsertirp.htm
tech.root: kernel
ms.assetid: ddfc0241-eab0-462b-8e1b-32bb9bcb3671
ms.date: 04/30/2018
keywords: ["IoCsqInsertIrp function"]
ms.keywords: IoCsqInsertIrp, IoCsqInsertIrp routine [Kernel-Mode Driver Architecture], k104_cecd79a7-3c42-45a2-99f7-54ca2a3e0358.xml, kernel.iocsqinsertirp, wdm/IoCsqInsertIrp
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - IoCsqInsertIrp
 - wdm/IoCsqInsertIrp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoCsqInsertIrp
---

# IoCsqInsertIrp function


## -description

The <b>IoCsqInsertIrp</b> routine inserts an IRP in the driver's cancel-safe IRP queue.

## -parameters

### -param Csq 

[in, out]
Pointer to the <a href="/windows-hardware/drivers/kernel/eprocess">IO_CSQ</a> structure for the driver's cancel-safe IRP queue. This structure must have been initialized by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize">IoCsqInitialize</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex">IoCsqInitializeEx</a>.

### -param Irp 

[in, out]
Pointer to the IRP to be queued.

### -param Context 

[out, optional]
Pointer to an <a href="/windows-hardware/drivers/kernel/eprocess">IO_CSQ_IRP_CONTEXT</a> structure. <b>IoCsqInsertIrp</b> initializes this structure with context information for the inserted IRP. The driver passes this value to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremoveirp">IoCsqRemoveIrp</a> to delete the IRP from the queue. <i>Context</i> can be <b>NULL</b> if the driver will not use <b>IoCsqRemoveIrp</b> to remove this IRP from the queue.

## -remarks

<b>IoCsqInsertIrp</b> uses the queue's dispatch routines to insert the IRP. The <b>IoCsqInsertIrp</b> routine:

<ol>
<li>
Calls the queue's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_acquire_lock">CsqAcquireLock</a> routine to lock the queue.

</li>
<li>
Calls the queue's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp">CsqInsertIrp</a> routine to insert the IRP.

</li>
<li>
Marks the IRP as pending.

</li>
<li>
Calls the queue's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_release_lock">CsqReleaseLock</a> routine to unlock the queue.

</li>
</ol>
If the IRP to be inserted has already been canceled, <b>IoCsqInsertIrp</b> does not attempt to insert the IRP into the queue.

Drivers can also use <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirpex">IoCsqInsertIrpEx</a> to insert an IRP into the queue. For a queue that is specified by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex">IoCsqInitializeEx</a>, <b>IoCsqInsertIrpEx</b> provides additional capabilities. For more information, see <a href="/windows-hardware/drivers/kernel/cancel-safe-irp-queues">Cancel-Safe IRP Queues</a>.

Note that the <b>IoCsq<i>Xxx</i></b> routines use the <b>DriverContext</b>[3] member of the IRP to hold IRP context information. Drivers that use these routines to queue IRPs must leave that member unused.

Callers of <b>IoCsqInsertIrp</b> must be running at an IRQL <= DISPATCH_LEVEL. The driver's callback routines must work correctly at that IRQL.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_acquire_lock">CsqAcquireLock</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_complete_canceled_irp">CsqCompleteCanceledIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp">CsqInsertIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp_ex">CsqInsertIrpEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_peek_next_irp">CsqPeekNextIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_release_lock">CsqReleaseLock</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_remove_irp">CsqRemoveIrp</a>



<a href="/windows-hardware/drivers/kernel/eprocess">IO_CSQ</a>



<a href="/windows-hardware/drivers/kernel/eprocess">IO_CSQ_IRP_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize">IoCsqInitialize</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex">IoCsqInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirpex">IoCsqInsertIrpEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremoveirp">IoCsqRemoveIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremovenextirp">IoCsqRemoveNextIrp</a>