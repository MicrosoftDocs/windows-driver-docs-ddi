---
UID: NF:wdm.IoCsqInsertIrpEx
title: IoCsqInsertIrpEx function
author: windows-driver-content
description: The IoCsqInsertIrpEx routine inserts an IRP into the driver's cancel-safe IRP queue.
old-location: kernel\iocsqinsertirpex.htm
old-project: kernel
ms.assetid: b1eb237d-ad4d-428c-beee-5f24677bd0d3
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k104_5a30f95f-f46d-4f45-a261-a740f33c5327.xml, wdm/IoCsqInsertIrpEx, IoCsqInsertIrpEx, kernel.iocsqinsertirpex, IoCsqInsertIrpEx routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of the Windows operating system. The routine is also available in the Csq.lib library that ships with the Windows Driver Kit (WDK) and the Driver Development Kit (DDK) for Windows Server 2003. Drivers that must also work for on Windows XP, Windows 2000, and Windows 98/Me can instead link to Csq.lib to use the routine.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoCsqInsertIrpEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoCsqInsertIrpEx function


## -description


The <b>IoCsqInsertIrpEx</b> routine inserts an IRP into the driver's cancel-safe IRP queue.


## -syntax


````
NTSTATUS IoCsqInsertIrpEx(
  _Inout_   PIO_CSQ             Csq,
  _Inout_   PIRP                Irp,
  _Out_opt_ PIO_CSQ_IRP_CONTEXT Context,
  _In_opt_  PVOID               InsertContext
);
````


## -parameters




### -param Csq [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure for the driver's cancel-safe IRP queue. This structure must have been initialized by <a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a> or <a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a>.


### -param Irp [in, out]

Pointer to the IRP to be queued.


### -param Context [out, optional]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550567">IO_CSQ_IRP_CONTEXT</a> structure. <b>IoCsqInsertIrpEx</b> initializes this structure with context information for the inserted IRP. The driver passes this value to <a href="..\wdm\nf-wdm-iocsqremoveirp.md">IoCsqRemoveIrp</a> to delete the IRP from the queue. <i>Context</i> can be <b>NULL</b> if the driver will not use <b>IoCsqRemoveIrp</b> to remove this IRP from the queue.


### -param InsertContext [in, optional]

Pointer to a driver-defined context value. This parameter is passed to the driver's <a href="..\wdm\nc-wdm-io_csq_insert_irp_ex.md">CsqInsertIrpEx</a> routine, if it has one. Otherwise, this parameter is ignored.


## -returns



If the <i>Csq</i> parameter was initialized with <a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a>, <b>IoCsqInsertIrpEx</b> always returns STATUS_SUCCESS. If <i>Csq</i> was initialized with <b>IoCsqInitializeEx</b>, <b>IoCsqInsertIrpEx</b> returns the value that was returned by the driver's <a href="..\wdm\nc-wdm-io_csq_insert_irp_ex.md">CsqInsertIrpEx</a> routine.




## -remarks



<b>IoCsqInsertIrpEx</b> uses the queue's dispatch routines to insert the IRP. The <b>IoCsqInsertIrpEx</b> routine:

<ol>
<li>
Calls the queue's <a href="..\wdm\nc-wdm-io_csq_acquire_lock.md">CsqAcquireLock</a> routine to lock the queue.

</li>
<li>
If the queue's <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure was initialized by <a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a>, <b>IoCsqInsertIrpEx</b> calls the queue's <a href="..\wdm\nc-wdm-io_csq_insert_irp.md">CsqInsertIrp</a> routine to insert the IRP. If the queue's <b>IO_CSQ</b> structure was initialized by <a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a>, <b>IoCsqInsertIrpEx</b> calls the queue's <a href="..\wdm\nc-wdm-io_csq_insert_irp_ex.md">CsqInsertIrpEx</a> routine to insert the IRP, and passes the <i>InsertContext</i> parameter as the <i>InsertContext</i> parameter of <i>CsqInsertIrpEx</i>.

</li>
<li>
Calls the queue's <a href="..\wdm\nc-wdm-io_csq_release_lock.md">CsqReleaseLock</a> routine to unlock the queue.

</li>
</ol>
If the IRP to be inserted has already been canceled, <b>IoCsqInsertIrpEx</b> does not attempt to insert the IRP into the queue.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.

Note that <b>IoCsq<i>Xxx</i></b> routines use the <b>DriverContext</b>[3] member of the IRP to hold IRP context information. Drivers that use these routines to queue IRPs must leave that member unused.

Callers of <b>IoCsqInsertIrpEx</b> must be running at an IRQL &lt;= DISPATCH_LEVEL. The driver's callback routines must work correctly at this IRQL. 




## -see-also

<a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a>



<a href="..\wdm\nc-wdm-io_csq_remove_irp.md">CsqRemoveIrp</a>



<a href="..\wdm\nf-wdm-iocsqinsertirp.md">IoCsqInsertIrp</a>



<a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a>



<a href="..\wdm\nc-wdm-io_csq_peek_next_irp.md">CsqPeekNextIrp</a>



<a href="..\wdm\nc-wdm-io_csq_insert_irp.md">CsqInsertIrp</a>



<a href="..\wdm\nf-wdm-iocsqremovenextirp.md">IoCsqRemoveNextIrp</a>



<a href="..\wdm\nc-wdm-io_csq_release_lock.md">CsqReleaseLock</a>



<a href="..\wdm\nc-wdm-io_csq_acquire_lock.md">CsqAcquireLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550567">IO_CSQ_IRP_CONTEXT</a>



<a href="..\wdm\nf-wdm-iocsqremoveirp.md">IoCsqRemoveIrp</a>



<a href="..\wdm\nc-wdm-io_csq_complete_canceled_irp.md">CsqCompleteCanceledIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a>



<a href="..\wdm\nc-wdm-io_csq_insert_irp_ex.md">CsqInsertIrpEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoCsqInsertIrpEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

