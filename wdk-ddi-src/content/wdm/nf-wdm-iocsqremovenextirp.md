---
UID: NF:wdm.IoCsqRemoveNextIrp
title: IoCsqRemoveNextIrp function (wdm.h)
description: The IoCsqRemoveNextIrp routine removes the next matching IRP in the queue.
old-location: kernel\iocsqremovenextirp.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoCsqRemoveNextIrp function"]
ms.keywords: IoCsqRemoveNextIrp, IoCsqRemoveNextIrp routine [Kernel-Mode Driver Architecture], k104_da0b9a4a-daa7-4085-ab2a-77b81856820f.xml, kernel.iocsqremovenextirp, wdm/IoCsqRemoveNextIrp
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows. Drivers that must also work on Windows 2000 and Windows 98/Me can instead link to Csq.lib to use the routine.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - IoCsqRemoveNextIrp
 - wdm/IoCsqRemoveNextIrp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoCsqRemoveNextIrp
---

# IoCsqRemoveNextIrp function


## -description

The <b>IoCsqRemoveNextIrp</b> routine removes the next matching IRP in the queue.

## -parameters

### -param Csq 

[in, out]
Pointer to the driver's dispatch table for cancel-safe IRP queues. The dispatch table must be initialized by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize">IoCsqInitialize</a>.

### -param PeekContext 

[in, optional]
A pointer to a driver-defined context value. <b>IoCsqRemoveNextIrp</b> passes this parameter to the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_peek_next_irp">CsqPeekNextIrp</a> routine. For more information, see the following Remarks section.

## -returns

This routine returns a pointer to the next matching IRP in the queue, or <b>NULL</b> if no more IRPs are available. The routine only returns IRPs that have not yet been canceled.

## -remarks

<b>IoCsqRemoveNextIrp</b> uses the queue's dispatch routines to remove the IRP. The <b>IoCsqRemoveNextIrp</b> routine:

<ol>
<li>
Calls the queue's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_acquire_lock">CsqAcquireLock</a> routine to lock the queue.

</li>
<li>
Calls the queue's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_peek_next_irp">CsqPeekNextIrp</a> routine to find the next matching IRP in the queue. <b>IoCsqRemoveNextIrp</b> passes the value of the <i>PeekContext</i> parameter as the <i>PeekContext</i> parameter of <i>CsqPeekNextIrp</i>. <i>CsqPeekNextIrp</i> returns a pointer to the next matching IRP, or <b>NULL</b> if there is no matching IRP.

</li>
<li>
If the return value of <i>CsqPeekNextIrp</i> is non-<b>NULL</b>, <b>IoCsqRemoveNextIrp</b> calls the queue's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_remove_irp">CsqRemoveIrp</a> routine to remove the IRP.

</li>
<li>
Calls the queue's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_release_lock">CsqReleaseLock</a> routine to unlock the queue.

</li>
</ol>
For more information, see <a href="/windows-hardware/drivers/kernel/cancel-safe-irp-queues">Cancel-Safe IRP Queues</a>.

Note that <b>IoCsq<i>Xxx</i></b> routines use the <b>DriverContext</b>[3] member of the IRP to hold IRP context information. Drivers that use these routines to queue IRPs must leave that member unused.

Callers of <b>IoCsqRemoveNextIrp</b> must be running at an IRQL <= DISPATCH_LEVEL. The driver's callback routines must work correctly at that IRQL.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_acquire_lock">CsqAcquireLock</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_complete_canceled_irp">CsqCompleteCanceledIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp">CsqInsertIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp_ex">CsqInsertIrpEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_peek_next_irp">CsqPeekNextIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_release_lock">CsqReleaseLock</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_remove_irp">CsqRemoveIrp</a>



<a href="/windows-hardware/drivers/kernel/eprocess">IO_CSQ</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize">IoCsqInitialize</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex">IoCsqInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirp">IoCsqInsertIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirpex">IoCsqInsertIrpEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremoveirp">IoCsqRemoveIrp</a>
