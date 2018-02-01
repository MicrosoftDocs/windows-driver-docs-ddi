---
UID: NC:wdm.IO_CSQ_COMPLETE_CANCELED_IRP
title: IO_CSQ_COMPLETE_CANCELED_IRP
author: windows-driver-content
description: The CsqCompleteCanceledIrp routine is used by the system to signal to the driver that it can complete a canceled IRP.
old-location: kernel\csqcompletecanceledirp.htm
old-project: kernel
ms.assetid: ed2f8529-dfc7-4db5-b90c-c0bf8840dc70
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.csqcompletecanceledirp, CsqCompleteCanceledIrp routine [Kernel-Mode Driver Architecture], CsqCompleteCanceledIrp, IO_CSQ_COMPLETE_CANCELED_IRP, IO_CSQ_COMPLETE_CANCELED_IRP, wdm/CsqCompleteCanceledIrp, DrvrRtns_07239a13-c445-4f75-8765-ff5806515ecb.xml
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	CsqCompleteCanceledIrp
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# IO_CSQ_COMPLETE_CANCELED_IRP callback


## -description


The <i>CsqCompleteCanceledIrp</i> routine is used by the system to signal to the driver that it can complete a canceled IRP.


## -prototype


````
IO_CSQ_COMPLETE_CANCELED_IRP CsqCompleteCanceledIrp;

VOID CsqCompleteCanceledIrp(
  _In_ PIO_CSQ Csq,
  _In_ PIRP    Irp
)
{ ... }
````


## -parameters




### -param Csq [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure for the cancel-safe IRP queue.


### -param Irp [in]

Pointer to the IRP to be canceled.


## -returns


None



## -remarks


The driver specifies the <i>CsqCompleteCanceledIrp</i> routine for a cancel-safe IRP queue when it initializes the queue's <b>IO_CSQ</b> structure. The driver specifies the routine as the <i>CsqCompleteCanceledIrp</i> parameter of <a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a> or <a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a> when it initializes <b>IO_CSQ</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.

The system calls this routine to complete a canceled IRP that has been removed from the driver's queue. Normally, drivers just call <a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a> for the IRP with a status of STATUS_CANCELLED.

Drivers are not required to remove the IRP from the queue before completing it as canceled: the system always calls the queue's <a href="..\wdm\nc-wdm-io_csq_remove_irp.md">CsqRemoveIrp</a> routine to remove the IRP from the queue before calling <i>CsqCompleteCanceledIrp</i>. 



## -see-also

<a href="..\wdm\nc-wdm-io_csq_insert_irp.md">CsqInsertIrp</a>

<a href="..\wdm\nf-wdm-iocsqinsertirp.md">IoCsqInsertIrp</a>

<a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a>

<a href="..\wdm\nc-wdm-io_csq_insert_irp_ex.md">CsqInsertIrpEx</a>

<a href="..\wdm\nf-wdm-iocsqremovenextirp.md">IoCsqRemoveNextIrp</a>

<a href="..\wdm\nc-wdm-io_csq_complete_canceled_irp.md">CsqCompleteCanceledIrp</a>

<a href="..\wdm\nf-wdm-iocsqinsertirpex.md">IoCsqInsertIrpEx</a>

<a href="..\wdm\nc-wdm-io_csq_release_lock.md">CsqReleaseLock</a>

<a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>

<a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a>

<a href="..\wdm\nc-wdm-io_csq_peek_next_irp.md">CsqPeekNextIrp</a>

<a href="..\wdm\nf-wdm-iocsqremoveirp.md">IoCsqRemoveIrp</a>

<a href="..\wdm\nc-wdm-io_csq_remove_irp.md">CsqRemoveIrp</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_CSQ_COMPLETE_CANCELED_IRP routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

