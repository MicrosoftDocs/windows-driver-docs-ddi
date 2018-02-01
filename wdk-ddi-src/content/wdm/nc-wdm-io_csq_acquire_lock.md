---
UID: NC:wdm.IO_CSQ_ACQUIRE_LOCK
title: IO_CSQ_ACQUIRE_LOCK
author: windows-driver-content
description: The CsqAcquireLock routine is used by the system to acquire the lock for a driver-implemented, cancel-safe IRP queue.
old-location: kernel\csqacquirelock.htm
old-project: kernel
ms.assetid: 8981e2f9-b456-48de-b31c-25a6884bcf12
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.csqacquirelock, CsqAcquireLock routine [Kernel-Mode Driver Architecture], CsqAcquireLock, IO_CSQ_ACQUIRE_LOCK, IO_CSQ_ACQUIRE_LOCK, wdm/CsqAcquireLock, DrvrRtns_02339dc6-f9f2-47b0-a0c9-df36f862b5d6.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	CsqAcquireLock
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# IO_CSQ_ACQUIRE_LOCK callback


## -description


The <i>CsqAcquireLock</i> routine is used by the system to acquire the lock for a driver-implemented, cancel-safe IRP queue.


## -prototype


````
IO_CSQ_ACQUIRE_LOCK CsqAcquireLock;

VOID CsqAcquireLock(
  _In_  PIO_CSQ Csq,
  _Out_ PKIRQL  Irql
)
{ ... }
````


## -parameters




### -param Csq [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure for the cancel-safe IRP queue.


### -param Irql [out]

Pointer to a variable that the <i>CsqAcquireLock</i> routine can use to store the current IRQL. The system passes the stored value <a href="..\wdm\nc-wdm-io_csq_release_lock.md">CsqReleaseLock</a> when it releases the lock.


## -returns


None



## -remarks


The driver specifies the <i>CsqAcquireLock</i> routine for a cancel-safe IRP queue when it initializes the queue's <b>IO_CSQ</b> structure. The driver specifies the routine as the <i>CsqAcquireLock</i> parameter of <a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a> or <a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a> when it initializes <b>IO_CSQ</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.

The system calls this routine to acquire a lock on the driver's IRP queue before attempting to insert or remove an IRP from the queue. The system calls the <a href="..\wdm\nc-wdm-io_csq_release_lock.md">CsqReleaseLock</a> routine to release the lock.

If the driver uses a spin lock to implement locking for the queue, it must store the current IRQL for when it releases the spin lock. The system passes a pointer to an IRQL variable that the driver can use to store the current IRQL. The system passes the stored value as the <i>Irql</i> parameter to <i>CsqReleaseLock</i> when it releases the lock. Otherwise the driver can ignore the <i>Irql</i> parameter. For information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>.

Drivers can use any locking mechanism to lock the queue, such as mutexes. For more information about mutexes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556417">Mutex Objects</a>.



## -see-also

<a href="..\wdm\nc-wdm-io_csq_insert_irp.md">CsqInsertIrp</a>

<a href="..\wdm\nf-wdm-iocsqinsertirp.md">IoCsqInsertIrp</a>

<a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a>

<a href="..\wdm\nc-wdm-io_csq_insert_irp_ex.md">CsqInsertIrpEx</a>

<a href="..\wdm\nf-wdm-iocsqremovenextirp.md">IoCsqRemoveNextIrp</a>

<a href="..\wdm\nc-wdm-io_csq_complete_canceled_irp.md">CsqCompleteCanceledIrp</a>

<a href="..\wdm\nf-wdm-iocsqinsertirpex.md">IoCsqInsertIrpEx</a>

<a href="..\wdm\nc-wdm-io_csq_release_lock.md">CsqReleaseLock</a>

<a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a>

<a href="..\wdm\nc-wdm-io_csq_peek_next_irp.md">CsqPeekNextIrp</a>

<a href="..\wdm\nf-wdm-iocsqremoveirp.md">IoCsqRemoveIrp</a>

<a href="..\wdm\nc-wdm-io_csq_remove_irp.md">CsqRemoveIrp</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_CSQ_ACQUIRE_LOCK routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

