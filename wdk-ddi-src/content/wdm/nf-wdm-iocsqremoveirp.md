---
UID: NF:wdm.IoCsqRemoveIrp
title: IoCsqRemoveIrp function
author: windows-driver-content
description: The IoCsqRemoveIrp routine removes a particular IRP from the queue.
old-location: kernel\iocsqremoveirp.htm
old-project: kernel
ms.assetid: 72a6327c-01b2-479c-a2eb-f58180193d50
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/IoCsqRemoveIrp, kernel.iocsqremoveirp, IoCsqRemoveIrp, k104_9a940115-fcbd-4e46-b7a5-10dc7fad7bda.xml, IoCsqRemoveIrp routine [Kernel-Mode Driver Architecture]
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoCsqRemoveIrp
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoCsqRemoveIrp function


## -description


The <b>IoCsqRemoveIrp</b> routine removes a particular IRP from the queue.


## -syntax


````
PIRP IoCsqRemoveIrp(
  _Inout_ PIO_CSQ             Csq,
  _Inout_ PIO_CSQ_IRP_CONTEXT Context
);
````


## -parameters




### -param Csq [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure for the driver's cancel-safe IRP queue. This structure must have been initialized by <a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a> or <a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a>.


### -param Context [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550567">IO_CSQ_IRP_CONTEXT</a> structure that identifies the IRP to remove. The <b>IO_CSQ_IRP_CONTEXT</b> structure is initialized by <a href="..\wdm\nf-wdm-iocsqinsertirp.md">IoCsqInsertIrp</a> or <a href="..\wdm\nf-wdm-iocsqinsertirpex.md">IoCsqInsertIrpEx</a> when the IRP is first inserted in the queue.


## -returns



This routine returns a pointer to the IRP that was removed from the queue, or <b>NULL</b> if that IRP has been canceled.




## -remarks



<b>IoCsqRemoveIrp</b> uses the queue's dispatch routines to remove the IRP. The <b>IoCsqRemoveIrp</b> routine:

<ol>
<li>
Calls the queue's <a href="..\wdm\nc-wdm-io_csq_acquire_lock.md">CsqAcquireLock</a> routine to lock the queue.

</li>
<li>
Uses the <i>IrpContext</i> parameter to determine which IRP to remove, and calls the queue's <a href="..\wdm\nc-wdm-io_csq_remove_irp.md">CsqRemoveIrp</a> routine to remove that IRP.

</li>
<li>
Calls the queue's <a href="..\wdm\nc-wdm-io_csq_release_lock.md">CsqReleaseLock</a> routine to unlock the queue.

</li>
</ol>
Drivers can use the <a href="..\wdm\nf-wdm-iocsqremovenextirp.md">IoCsqRemoveNextIrp</a> routine to remove an IRP that matches a specific criterion. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.

Note that <b>IoCsq<i>Xxx</i></b> routines use the <b>DriverContext[</b>3<b>]</b> member of the IRP to hold IRP context information. Drivers that use these routines to queue IRPs must leave that member unused.

Callers of <b>IoCsqRemoveIrp</b> must be running at an IRQL &lt;= DISPATCH_LEVEL. The driver's callback routines must work correctly at that IRQL.




## -see-also

<a href="..\wdm\nc-wdm-io_csq_insert_irp_ex.md">CsqInsertIrpEx</a>



<a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a>



<a href="..\wdm\nf-wdm-iocsqinsertirp.md">IoCsqInsertIrp</a>



<a href="..\wdm\nc-wdm-io_csq_complete_canceled_irp.md">CsqCompleteCanceledIrp</a>



<a href="..\wdm\nf-wdm-iocsqremovenextirp.md">IoCsqRemoveNextIrp</a>



<a href="..\wdm\nf-wdm-iocsqinsertirpex.md">IoCsqInsertIrpEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550567">IO_CSQ_IRP_CONTEXT</a>



<a href="..\wdm\nc-wdm-io_csq_remove_irp.md">CsqRemoveIrp</a>



<a href="..\wdm\nc-wdm-io_csq_release_lock.md">CsqReleaseLock</a>



<a href="..\wdm\nc-wdm-io_csq_peek_next_irp.md">CsqPeekNextIrp</a>



<a href="..\wdm\nc-wdm-io_csq_insert_irp.md">CsqInsertIrp</a>



<a href="..\wdm\nc-wdm-io_csq_acquire_lock.md">CsqAcquireLock</a>



<a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoCsqRemoveIrp routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

