---
UID: NC:wdm.IO_CSQ_REMOVE_IRP
title: IO_CSQ_REMOVE_IRP
author: windows-driver-content
description: The CsqRemoveIrp routine is used by the system to remove the specified IRP from a driver-implemented, cancel-safe IRP queue.
old-location: kernel\csqremoveirp.htm
old-project: kernel
ms.assetid: 9d99a20b-3a95-4e27-96bd-41f38a631573
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.csqremoveirp, CsqRemoveIrp routine [Kernel-Mode Driver Architecture], CsqRemoveIrp, IO_CSQ_REMOVE_IRP, IO_CSQ_REMOVE_IRP, wdm/CsqRemoveIrp, DrvrRtns_6d9086c3-65b8-4e0e-b5e9-0c4edbf513b1.xml
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
-	CsqRemoveIrp
product: Windows
targetos: Windows
req.typenames: "*PWDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME"
req.product: Windows 10 or later.
---

# IO_CSQ_REMOVE_IRP callback


## -description


The <i>CsqRemoveIrp</i> routine is used by the system to remove the specified IRP from a driver-implemented, cancel-safe IRP queue.


## -prototype


````
IO_CSQ_REMOVE_IRP CsqRemoveIrp;

VOID CsqRemoveIrp(
  _In_ PIO_CSQ Csq,
  _In_ PIRP    Irp
)
{ ... }
````


## -parameters




### -param Csq [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure for the cancel-safe IRP queue.


### -param Irp [in]

Pointer to the IRP to remove from the IRP queue. 


## -returns


None



## -remarks


The driver specifies the <i>CsqRemoveIrp</i> routine for a cancel-safe IRP queue when it initializes the queue's <b>IO_CSQ</b> structure. The driver specifies the routine as the <i>CsqRemoveIrp</i> parameter of <a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a> or <a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a> when it initializes <b>IO_CSQ</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.

The <a href="..\wdm\nf-wdm-iocsqremoveirp.md">IoCsqRemoveIrp</a> and <a href="..\wdm\nf-wdm-iocsqremovenextirp.md">IoCsqRemoveNextIrp</a> routines call the cancel-safe IRP queue's <i>CsqRemoveIrp</i> routine to remove the specified IRP from the queue. The system also uses <i>CsqRemoveIrp</i> to remove a canceled IRP from the queue.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a>

<a href="..\wdm\nf-wdm-iocsqremovenextirp.md">IoCsqRemoveNextIrp</a>

<a href="..\wdm\nc-wdm-io_csq_insert_irp.md">CsqInsertIrp</a>

<a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a>

<a href="..\wdm\nc-wdm-io_csq_insert_irp_ex.md">CsqInsertIrpEx</a>

<a href="..\wdm\nc-wdm-io_csq_complete_canceled_irp.md">CsqCompleteCanceledIrp</a>

<a href="..\wdm\nf-wdm-iocsqinsertirp.md">IoCsqInsertIrp</a>

<a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a>

<a href="..\wdm\nf-wdm-iocsqinsertirpex.md">IoCsqInsertIrpEx</a>

<a href="..\wdm\nc-wdm-io_csq_release_lock.md">CsqReleaseLock</a>

<a href="..\wdm\nc-wdm-io_csq_peek_next_irp.md">CsqPeekNextIrp</a>

<a href="..\wdm\nf-wdm-iocsqremoveirp.md">IoCsqRemoveIrp</a>

<a href="..\wdm\nc-wdm-io_csq_acquire_lock.md">CsqAcquireLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_CSQ_REMOVE_IRP routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

