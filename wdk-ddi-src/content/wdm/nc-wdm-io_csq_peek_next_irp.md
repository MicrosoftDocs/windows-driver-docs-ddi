---
UID: NC:wdm.IO_CSQ_PEEK_NEXT_IRP
title: IO_CSQ_PEEK_NEXT_IRP (wdm.h)
description: The CsqPeekNextIrp routine is used by the system to find the next matching IRP in a driver-implemented, cancel-safe IRP queue.
old-location: kernel\csqpeeknextirp.htm
tech.root: kernel
ms.assetid: 0968fea0-4c66-497f-8a01-baacc90b2458
ms.date: 04/30/2018
keywords: ["IO_CSQ_PEEK_NEXT_IRP callback function"]
ms.keywords: CsqPeekNextIrp, CsqPeekNextIrp routine [Kernel-Mode Driver Architecture], DrvrRtns_83ba77b2-17fa-4fdc-bfaf-c41289f54da9.xml, IO_CSQ_PEEK_NEXT_IRP, kernel.csqpeeknextirp, wdm/CsqPeekNextIrp
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IO_CSQ_PEEK_NEXT_IRP
 - wdm/IO_CSQ_PEEK_NEXT_IRP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - CsqPeekNextIrp
---

# IO_CSQ_PEEK_NEXT_IRP callback function


## -description

The <i>CsqPeekNextIrp</i> routine is used by the system to find the next matching IRP in a driver-implemented, cancel-safe IRP queue.

## -parameters

### -param Csq 

[in]
Pointer to the <a href="/windows-hardware/drivers/kernel/eprocess">IO_CSQ</a> structure for the cancel-safe IRP queue.

### -param Irp 

[in, optional]
Pointer to an IRP in the driver's IRP queue, or <b>NULL</b> to specify the beginning of the queue.

### -param PeekContext 

[in, optional]
Pointer to driver-defined context information. The <i>CsqPeekNextIrp</i> routine returns the first IRP that follows <i>Irp</i> and matches <i>PeekContext</i>.

## -returns

<i>CsqPeekNextIrp</i> returns the first IRP that follows <i>Irp</i> in the queue and matches <i>PeekContext</i>, or <b>NULL</b> if there is no matching IRP. If <i>Irp</i> is <b>NULL</b>, <i>CsqPeekNextIrp</i> returns the first matching IRP in the queue, or <b>NULL</b> if there is no matching IRP.

## -remarks

The driver specifies the <i>CsqPeekNextIrp</i> routine for a cancel-safe IRP queue when it initializes the queue's <b>IO_CSQ</b> structure. The driver specifies the routine as the <i>CsqPeekNextIrp</i> parameter of <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize">IoCsqInitialize</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex">IoCsqInitializeEx</a> when it initializes <b>IO_CSQ</b>. For more information, see <a href="/windows-hardware/drivers/kernel/cancel-safe-irp-queues">Cancel-Safe IRP Queues</a>.

The system uses <i>CsqPeekNextIrp</i> to iterate through the IRPs in the driver's IRP queue. For example, the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremovenextirp">IoCsqRemoveNextIrp</a> routine uses this routine to find the IRP to be removed.


#### Examples

To define a <i>CsqPeekNextIrp</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CsqPeekNextIrp</i> callback routine that is named <code>MyCsqPeekNextIrp</code>, use the IO_CSQ_PEEK_NEXT_IRP type as shown in this code example:


```
IO_CSQ_PEEK_NEXT_IRP MyCsqPeekNextIrp;
```

Then, implement your callback routine as follows:


```
_Use_decl_annotations_
PIRP 
 MyCsqPeekNextIrp(
    PIO_CSQ  Csq,
    PIRP  Irp,
    PVOID  PeekContext
    )
  {
      // Function body
  }
```

The IO_CSQ_PEEK_NEXT_IRP function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the IO_CSQ_PEEK_NEXT_IRP function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_acquire_lock">CsqAcquireLock</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_complete_canceled_irp">CsqCompleteCanceledIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp">CsqInsertIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp_ex">CsqInsertIrpEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_release_lock">CsqReleaseLock</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_remove_irp">CsqRemoveIrp</a>



<a href="/windows-hardware/drivers/kernel/eprocess">IO_CSQ</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize">IoCsqInitialize</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex">IoCsqInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirp">IoCsqInsertIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirpex">IoCsqInsertIrpEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremoveirp">IoCsqRemoveIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremovenextirp">IoCsqRemoveNextIrp</a>