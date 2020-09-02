---
UID: NC:wdm.IO_CSQ_COMPLETE_CANCELED_IRP
title: IO_CSQ_COMPLETE_CANCELED_IRP (wdm.h)
description: The CsqCompleteCanceledIrp routine is used by the system to signal to the driver that it can complete a canceled IRP.
old-location: kernel\csqcompletecanceledirp.htm
tech.root: kernel
ms.assetid: ed2f8529-dfc7-4db5-b90c-c0bf8840dc70
ms.date: 04/30/2018
keywords: ["IO_CSQ_COMPLETE_CANCELED_IRP callback function"]
ms.keywords: CsqCompleteCanceledIrp, CsqCompleteCanceledIrp routine [Kernel-Mode Driver Architecture], DrvrRtns_07239a13-c445-4f75-8765-ff5806515ecb.xml, IO_CSQ_COMPLETE_CANCELED_IRP, kernel.csqcompletecanceledirp, wdm/CsqCompleteCanceledIrp
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
 - IO_CSQ_COMPLETE_CANCELED_IRP
 - wdm/IO_CSQ_COMPLETE_CANCELED_IRP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - CsqCompleteCanceledIrp
---

# IO_CSQ_COMPLETE_CANCELED_IRP callback function


## -description

The <i>CsqCompleteCanceledIrp</i> routine is used by the system to signal to the driver that it can complete a canceled IRP.

## -parameters

### -param Csq 

[in]
Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_CSQ</a> structure for the cancel-safe IRP queue.

### -param Irp 

[in]
Pointer to the IRP to be canceled.

## -remarks

The driver specifies the <i>CsqCompleteCanceledIrp</i> routine for a cancel-safe IRP queue when it initializes the queue's <b>IO_CSQ</b> structure. The driver specifies the routine as the <i>CsqCompleteCanceledIrp</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize">IoCsqInitialize</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex">IoCsqInitializeEx</a> when it initializes <b>IO_CSQ</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/cancel-safe-irp-queues">Cancel-Safe IRP Queues</a>.

The system calls this routine to complete a canceled IRP that has been removed from the driver's queue. Normally, drivers just call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a> for the IRP with a status of STATUS_CANCELLED.

Drivers are not required to remove the IRP from the queue before completing it as canceled: the system always calls the queue's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_remove_irp">CsqRemoveIrp</a> routine to remove the IRP from the queue before calling <i>CsqCompleteCanceledIrp</i>. 


#### Examples

To define a <i>CsqCompleteCanceledIrp</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CsqCompleteCanceledIrp</i> callback routine that is named <code>MyCsqCompleteCanceledIrp</code>, use the IO_CSQ_COMPLETE_CANCELED_IRP type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IO_CSQ_COMPLETE_CANCELED_IRP MyCsqCompleteCanceledIrp;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID 
 MyCsqCompleteCanceledIrp(
    _In_ PIO_CSQ  Csq,
    _In_ PIRP  Irp
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The IO_CSQ_COMPLETE_CANCELED_IRP function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the IO_CSQ_COMPLETE_CANCELED_IRP function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_complete_canceled_irp">CsqCompleteCanceledIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp">CsqInsertIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp_ex">CsqInsertIrpEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_peek_next_irp">CsqPeekNextIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_release_lock">CsqReleaseLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_remove_irp">CsqRemoveIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_CSQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize">IoCsqInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex">IoCsqInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirp">IoCsqInsertIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirpex">IoCsqInsertIrpEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremoveirp">IoCsqRemoveIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremovenextirp">IoCsqRemoveNextIrp</a>

