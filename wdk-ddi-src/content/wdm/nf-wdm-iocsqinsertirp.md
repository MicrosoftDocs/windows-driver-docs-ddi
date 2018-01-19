---
UID: NF:wdm.IoCsqInsertIrp
title: IoCsqInsertIrp function
author: windows-driver-content
description: The IoCsqInsertIrp routine inserts an IRP in the driver's cancel-safe IRP queue.
old-location: kernel\iocsqinsertirp.htm
old-project: kernel
ms.assetid: ddfc0241-eab0-462b-8e1b-32bb9bcb3671
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoCsqInsertIrp
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
req.alt-api: IoCsqInsertIrp
req.alt-loc: NtosKrnl.exe
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoCsqInsertIrp function



## -description
The <b>IoCsqInsertIrp</b> routine inserts an IRP in the driver's cancel-safe IRP queue.



## -syntax

````
VOID IoCsqInsertIrp(
  _Inout_   PIO_CSQ             Csq,
  _Inout_   PIRP                Irp,
  _Out_opt_ PIO_CSQ_IRP_CONTEXT Context
);
````


## -parameters

### -param Csq [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure for the driver's cancel-safe IRP queue. This structure must have been initialized by <a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a> or <a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a>. 


### -param Irp [in, out]

Pointer to the IRP to be queued.


### -param Context [out, optional]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550567">IO_CSQ_IRP_CONTEXT</a> structure. <b>IoCsqInsertIrp</b> initializes this structure with context information for the inserted IRP. The driver passes this value to <a href="..\wdm\nf-wdm-iocsqremoveirp.md">IoCsqRemoveIrp</a> to delete the IRP from the queue. <i>Context</i> can be <b>NULL</b> if the driver will not use <b>IoCsqRemoveIrp</b> to remove this IRP from the queue. 


## -returns
None


## -remarks
<b>IoCsqInsertIrp</b> uses the queue's dispatch routines to insert the IRP. The <b>IoCsqInsertIrp</b> routine:

Calls the queue's <a href="..\wdm\nc-wdm-io_csq_acquire_lock.md">CsqAcquireLock</a> routine to lock the queue.

Calls the queue's <a href="..\wdm\nc-wdm-io_csq_insert_irp.md">CsqInsertIrp</a> routine to insert the IRP.

Marks the IRP as pending.

Calls the queue's <a href="..\wdm\nc-wdm-io_csq_release_lock.md">CsqReleaseLock</a> routine to unlock the queue.

If the IRP to be inserted has already been canceled, <b>IoCsqInsertIrp</b> does not attempt to insert the IRP into the queue.

Drivers can also use <a href="..\wdm\nf-wdm-iocsqinsertirpex.md">IoCsqInsertIrpEx</a> to insert an IRP into the queue. For a queue that is specified by <a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a>, <b>IoCsqInsertIrpEx</b> provides additional capabilities. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.

Note that the <b>IoCsq<i>Xxx</i></b> routines use the <b>DriverContext</b>[3] member of the IRP to hold IRP context information. Drivers that use these routines to queue IRPs must leave that member unused.

Callers of <b>IoCsqInsertIrp</b> must be running at an IRQL &lt;= DISPATCH_LEVEL. The driver's callback routines must work correctly at that IRQL.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550567">IO_CSQ_IRP_CONTEXT</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocsqinsertirpex.md">IoCsqInsertIrpEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocsqremoveirp.md">IoCsqRemoveIrp</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocsqremovenextirp.md">IoCsqRemoveNextIrp</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io_csq_acquire_lock.md">CsqAcquireLock</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io_csq_complete_canceled_irp.md">CsqCompleteCanceledIrp</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io_csq_insert_irp.md">CsqInsertIrp</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io_csq_insert_irp_ex.md">CsqInsertIrpEx</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io_csq_peek_next_irp.md">CsqPeekNextIrp</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io_csq_release_lock.md">CsqReleaseLock</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io_csq_remove_irp.md">CsqRemoveIrp</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoCsqInsertIrp routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

