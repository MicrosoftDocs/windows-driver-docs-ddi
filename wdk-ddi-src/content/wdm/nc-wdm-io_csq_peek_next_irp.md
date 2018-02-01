---
UID: NC:wdm.IO_CSQ_PEEK_NEXT_IRP
title: IO_CSQ_PEEK_NEXT_IRP
author: windows-driver-content
description: The CsqPeekNextIrp routine is used by the system to find the next matching IRP in a driver-implemented, cancel-safe IRP queue.
old-location: kernel\csqpeeknextirp.htm
old-project: kernel
ms.assetid: 0968fea0-4c66-497f-8a01-baacc90b2458
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.csqpeeknextirp, CsqPeekNextIrp routine [Kernel-Mode Driver Architecture], CsqPeekNextIrp, IO_CSQ_PEEK_NEXT_IRP, IO_CSQ_PEEK_NEXT_IRP, wdm/CsqPeekNextIrp, DrvrRtns_83ba77b2-17fa-4fdc-bfaf-c41289f54da9.xml
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
-	CsqPeekNextIrp
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# IO_CSQ_PEEK_NEXT_IRP callback


## -description


The <i>CsqPeekNextIrp</i> routine is used by the system to find the next matching IRP in a driver-implemented, cancel-safe IRP queue.


## -prototype


````
IO_CSQ_PEEK_NEXT_IRP CsqPeekNextIrp;

PIRP CsqPeekNextIrp(
  _In_     PIO_CSQ Csq,
  _In_opt_ PIRP    Irp,
  _In_opt_ PVOID   PeekContext
)
{ ... }
````


## -parameters




### -param Csq [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure for the cancel-safe IRP queue.


### -param Irp [in, optional]

Pointer to an IRP in the driver's IRP queue, or <b>NULL</b> to specify the beginning of the queue.


### -param PeekContext [in, optional]

Pointer to driver-defined context information. The <i>CsqPeekNextIrp</i> routine returns the first IRP that follows <i>Irp</i> and matches <i>PeekContext</i>.


## -returns


<i>CsqPeekNextIrp</i> returns the first IRP that follows <i>Irp</i> in the queue and matches <i>PeekContext</i>, or <b>NULL</b> if there is no matching IRP. If <i>Irp</i> is <b>NULL</b>, <i>CsqPeekNextIrp</i> returns the first matching IRP in the queue, or <b>NULL</b> if there is no matching IRP.



## -remarks


The driver specifies the <i>CsqPeekNextIrp</i> routine for a cancel-safe IRP queue when it initializes the queue's <b>IO_CSQ</b> structure. The driver specifies the routine as the <i>CsqPeekNextIrp</i> parameter of <a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a> or <a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a> when it initializes <b>IO_CSQ</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.

The system uses <i>CsqPeekNextIrp</i> to iterate through the IRPs in the driver's IRP queue. For example, the <a href="..\wdm\nf-wdm-iocsqremovenextirp.md">IoCsqRemoveNextIrp</a> routine uses this routine to find the IRP to be removed.



## -see-also

<a href="..\wdm\nc-wdm-io_csq_acquire_lock.md">CsqAcquireLock</a>

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

<a href="..\wdm\nf-wdm-iocsqremoveirp.md">IoCsqRemoveIrp</a>

<a href="..\wdm\nc-wdm-io_csq_remove_irp.md">CsqRemoveIrp</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_CSQ_PEEK_NEXT_IRP routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

