---
UID: NC:wdm.IO_CSQ_INSERT_IRP_EX
title: IO_CSQ_INSERT_IRP_EX
author: windows-driver-content
description: The CsqInsertIrpEx routine is used by the system to insert an IRP into a driver-implemented, cancel-safe IRP queue.
old-location: kernel\csqinsertirpex.htm
old-project: kernel
ms.assetid: 1e407bcc-0a2b-42fa-982d-8ab0f12f082b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.csqinsertirpex, CsqInsertIrpEx routine [Kernel-Mode Driver Architecture], CsqInsertIrpEx, IO_CSQ_INSERT_IRP_EX, IO_CSQ_INSERT_IRP_EX, wdm/CsqInsertIrpEx, DrvrRtns_8914d2b4-6049-4d81-8f5f-4458b8bff2ed.xml
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
-	CsqInsertIrpEx
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# IO_CSQ_INSERT_IRP_EX callback


## -description


The <i>CsqInsertIrpEx</i> routine is used by the system to insert an IRP into a driver-implemented, cancel-safe IRP queue.


## -prototype


````
IO_CSQ_INSERT_IRP_EX CsqInsertIrpEx;

NTSTATUS CsqInsertIrpEx(
  _In_ struct _IO_CSQ *Csq,
  _In_ PIRP           Irp,
  _In_ PVOID          InsertContext
)
{ ... }
````


## -parameters




### -param *Csq [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure for the cancel-safe IRP queue.


### -param Irp [in]

Pointer to the IRP to insert into the IRP queue.


### -param InsertContext [in]

Pointer to driver-defined context for the insert operation.


## -returns


<i>CsqInsertIrpEx</i> returns STATUS_SUCCESS if the IRP has been successfully inserted, or the appropriate error code on failure.



## -remarks


The driver specifies the <i>CsqInsertIrpEx</i> routine for a cancel-safe IRP queue when it initializes the queue's <b>IO_CSQ</b> structure. The driver specifies the routine as the <i>CsqInsertIrp</i> parameter of <a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a> when it initializes <b>IO_CSQ</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.

The <a href="..\wdm\nf-wdm-iocsqinsertirpex.md">IoCsqInsertIrpEx</a> routine calls <i>CsqInsertIrpEx</i> to insert the IRP into the queue. The <i>InsertContext</i> parameter of <b>IoCsqInsertIrpEx</b> is passed as the <i>InsertContext</i> parameter of <i>CsqInsertIrpEx</i>.



## -see-also

<a href="..\wdm\nc-wdm-io_csq_insert_irp.md">CsqInsertIrp</a>

<a href="..\wdm\nf-wdm-iocsqremoveirp.md">IoCsqRemoveIrp</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a>

<a href="..\wdm\nc-wdm-io_csq_complete_canceled_irp.md">CsqCompleteCanceledIrp</a>

<a href="..\wdm\nc-wdm-io_csq_remove_irp.md">CsqRemoveIrp</a>

<a href="..\wdm\nf-wdm-iocsqremovenextirp.md">IoCsqRemoveNextIrp</a>

<a href="..\wdm\nc-wdm-io_csq_release_lock.md">CsqReleaseLock</a>

<a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a>

<a href="..\wdm\nc-wdm-io_csq_acquire_lock.md">CsqAcquireLock</a>

<a href="..\wdm\nf-wdm-iocsqinsertirp.md">IoCsqInsertIrp</a>

<a href="..\wdm\nc-wdm-io_csq_peek_next_irp.md">CsqPeekNextIrp</a>

<a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a>

<a href="..\wdm\nf-wdm-iocsqinsertirpex.md">IoCsqInsertIrpEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_CSQ_INSERT_IRP_EX routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

