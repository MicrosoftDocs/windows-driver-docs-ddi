---
UID: NC:wdm.IO_CSQ_INSERT_IRP_EX
title: IO_CSQ_INSERT_IRP_EX (wdm.h)
description: The CsqInsertIrpEx routine is used by the system to insert an IRP into a driver-implemented, cancel-safe IRP queue.
old-location: kernel\csqinsertirpex.htm
tech.root: kernel
ms.assetid: 1e407bcc-0a2b-42fa-982d-8ab0f12f082b
ms.date: 04/30/2018
keywords: ["IO_CSQ_INSERT_IRP_EX callback function"]
ms.keywords: CsqInsertIrpEx, CsqInsertIrpEx routine [Kernel-Mode Driver Architecture], DrvrRtns_8914d2b4-6049-4d81-8f5f-4458b8bff2ed.xml, IO_CSQ_INSERT_IRP_EX, kernel.csqinsertirpex, wdm/CsqInsertIrpEx
f1_keywords:
 - "wdm/CsqInsertIrpEx"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- CsqInsertIrpEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IO_CSQ_INSERT_IRP_EX callback function


## -description


The <i>CsqInsertIrpEx</i> routine is used by the system to insert an IRP into a driver-implemented, cancel-safe IRP queue.


## -parameters




### -param Csq [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_CSQ</a> structure for the cancel-safe IRP queue.


### -param Irp [in]

Pointer to the IRP to insert into the IRP queue.


### -param InsertContext [in]

Pointer to driver-defined context for the insert operation.


## -returns



<i>CsqInsertIrpEx</i> returns STATUS_SUCCESS if the IRP has been successfully inserted, or the appropriate error code on failure.




## -remarks



The driver specifies the <i>CsqInsertIrpEx</i> routine for a cancel-safe IRP queue when it initializes the queue's <b>IO_CSQ</b> structure. The driver specifies the routine as the <i>CsqInsertIrp</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex">IoCsqInitializeEx</a> when it initializes <b>IO_CSQ</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/cancel-safe-irp-queues">Cancel-Safe IRP Queues</a>.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirpex">IoCsqInsertIrpEx</a> routine calls <i>CsqInsertIrpEx</i> to insert the IRP into the queue. The <i>InsertContext</i> parameter of <b>IoCsqInsertIrpEx</b> is passed as the <i>InsertContext</i> parameter of <i>CsqInsertIrpEx</i>.


#### Examples

To define a <i>CsqInsertIrpEx</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CsqInsertIrpEx</i> callback routine that is named <code>MyCsqInsertIrpEx</code>, use the IO_CSQ_INSERT_IRP_EX type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IO_CSQ_INSERT_IRP_EX MyCsqInsertIrpEx;</pre>
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
NTSTATUS
 MyCsqInsertIrpEx(
    struct _IO_CSQ  *Csq,
    PIRP  Irp,
    PVOID  InsertContext
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The IO_CSQ_INSERT_IRP_EX function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the IO_CSQ_INSERT_IRP_EX function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_acquire_lock">CsqAcquireLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_complete_canceled_irp">CsqCompleteCanceledIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp">CsqInsertIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_peek_next_irp">CsqPeekNextIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_release_lock">CsqReleaseLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_remove_irp">CsqRemoveIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_CSQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize">IoCsqInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex">IoCsqInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirp">IoCsqInsertIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirpex">IoCsqInsertIrpEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremoveirp">IoCsqRemoveIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremovenextirp">IoCsqRemoveNextIrp</a>
 

 

