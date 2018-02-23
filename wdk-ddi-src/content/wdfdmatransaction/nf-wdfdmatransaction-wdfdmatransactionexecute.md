---
UID: NF:wdfdmatransaction.WdfDmaTransactionExecute
title: WdfDmaTransactionExecute function
author: windows-driver-content
description: The WdfDmaTransactionExecute method begins the execution of a specified DMA transaction.
old-location: wdf\wdfdmatransactionexecute.htm
old-project: wdf
ms.assetid: 8f52557f-b65d-479d-aab4-1e4f7298c8f9
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfDmaTransactionExecute method, wdf.wdfdmatransactionexecute, WdfDmaTransactionExecute, DFDmaObjectRef_012a66e9-0ed7-458f-9068-c7d2ce58d86a.xml, kmdf.wdfdmatransactionexecute, wdfdmatransaction/WdfDmaTransactionExecute
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDmaTransactionExecute
product: Windows
targetos: Windows
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---

# WdfDmaTransactionExecute function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionExecute</b> method begins the execution of a specified DMA transaction. 


## -syntax


````
NTSTATUS WdfDmaTransactionExecute(
  _In_     WDFDMATRANSACTION DmaTransaction,
  _In_opt_ WDFCONTEXT        Context
);
````


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>.


### -param Context [in, optional]

Driver-defined context information. The framework passes the value specified for <i>Context</i>, which can be a pointer, to the driver's <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> event callback function. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>WdfDmaTransactionExecute</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The driver previously called <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsetimmediateexecution.md">WdfDmaTransactionSetImmediateExecution</a> and the resources needed for the request are unavailable.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionexecute.md">WdfDmaTransactionExecute</a> was not preceded by a call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitialize.md">WdfDmaTransactionInitialize</a> or <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest.md">WdfDmaTransactionInitializeUsingRequest</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_BUSY</b></dt>
</dl>
</td>
<td width="60%">
The device performs single-packet transfers, and the driver called <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionexecute.md">WdfDmaTransactionExecute</a> while another transaction was executing.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_TOO_FRAGMENTED</b></dt>
</dl>
</td>
<td width="60%">
The number of scatter/gather elements that the operating system needed to handle the specified transfer size was greater than the value that the driver's call to <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablersetmaximumscattergatherelements.md">WdfDmaEnablerSetMaximumScatterGatherElements</a> specified. For more information, see the following Remarks section.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfDmaTransactionExecute</b> method initializes a transaction's scatter/gather list for the first <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transfer</a> that is associated with the specified <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transaction</a>. (For single-packet transfers, the scatter/gather list contains a single element.) Then, the method calls the driver's <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> event callback function, and the callback function can program the device to begin the transfer. 

Framework-based drivers typically call <b>WdfDmaTransactionExecute</b> from within an <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">I/O queue event callback function</a>. 

After a driver has called <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitialize.md">WdfDmaTransactionInitialize</a> or <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest.md">WdfDmaTransactionInitializeUsingRequest</a> to initialize a DMA transaction, the driver must call <b>WdfDmaTransactionExecute</b> only once before <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-a-dma-transaction">completing the DMA transaction</a>. 


          If <b>WdfDmaTransactionInitialize<i>Xxx</i></b> returns success but <b>WdfDmaTransactionExecute</b> returns an error value, your driver must call <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionrelease.md">WdfDmaTransactionRelease</a>.

In framework versions prior to 1.11, if the device performs single-packet transfers, the operating system can execute only one DMA transaction at a time. In this case, <b>WdfDmaTransactionExecute</b> returns STATUS_WDF_BUSY if another transaction is executing.

In framework versions 1.11 and later, if the driver uses DMA version 3 to perform single-packet transfers, the operating system can store multiple DMA transactions in an internal queue. In this case, the driver can call <b>WdfDmaTransactionExecute</b> while another transaction is executing. To select DMA version 3, set the <b>WdmDmaVersionOverride</b> member of <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a> to 3.

If the device performs scatter/gather transfers, the operating system can execute multiple DMA transactions simultaneously. In this case, the driver can call <b>WdfDmaTransactionExecute</b> while another transaction is executing.

If the driver calls <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedwithlength.md">WdfDmaTransactionDmaCompletedWithLength</a> to report a partial transfer, and if the driver had specified the DMA transaction's data buffer by using MDLs that it chained together (using the <b>Next</b> member of the <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> structure), <b>WdfDmaTransactionExecute</b> can return STATUS_WDF_TOO_FRAGMENTED because the framework might recalculate the number and size of fragments and might exceed the number of allowed fragments.

The <b>WdfDmaTransactionExecute</b> returns STATUS_SUCCESS if the transaction was successfully started. To determine if the framework successfully sent all of the transaction's transfers to the driver's <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> callback function, the driver must call <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompleted.md">WdfDmaTransactionDmaCompleted</a>, <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedwithlength.md">WdfDmaTransactionDmaCompletedWithLength</a>, or <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal.md">WdfDmaTransactionDmaCompletedFinal</a>.

If the value that the <i>Context</i> parameter supplies is a pointer or handle, the memory that it references must be accessible in the driver's <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> event callback function at IRQL = DISPATCH_LEVEL. You can use <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-context-space">framework object context</a> to meet this requirement.

The driver can call <b>WdfDmaTransactionExecute</b> in a non-blocking manner if it has previously called <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsetimmediateexecution.md">WdfDmaTransactionSetImmediateExecution</a>.

For more information about DMA transactions, see <a href="https://msdn.microsoft.com/fa26ef08-01c0-4502-9cb3-865000242e4a">Starting a DMA Transaction</a>.


#### Examples

The following code example is from the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">PCIDRV</a> sample driver. This example creates and initializes a DMA transfer and begins its execution.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
NICInitiateDmaTransfer(
    IN PFDO_DATA  FdoData,
    IN WDFREQUEST  Request
    )
{
    WDFDMATRANSACTION  dmaTransaction;
    NTSTATUS  status;
    BOOLEAN  bCreated = FALSE;
 
    do {
        status = WdfDmaTransactionCreate(
                                         FdoData-&gt;WdfDmaEnabler,
                                         WDF_NO_OBJECT_ATTRIBUTES,
                                         &amp;dmaTransaction
                                         );
        if(!NT_SUCCESS(status)) {
            TraceEvents(TRACE_LEVEL_ERROR, DBG_WRITE, 
                        "WdfDmaTransactionCreate failed %X\n", status);
            break;
        }

        bCreated = TRUE;

        status = WdfDmaTransactionInitializeUsingRequest( 
                                     dmaTransaction,
                                     Request,
                                     NICEvtProgramDmaFunction,
                                     WdfDmaDirectionWriteToDevice
                                     );
        if(!NT_SUCCESS(status)) {
            TraceEvents(
                        TRACE_LEVEL_ERROR,
                        DBG_WRITE, 
                        "WdfDmaTransactionInitalizeUsingRequest failed %X\n", 
                        status
                        );
            break;
        }

        status = WdfDmaTransactionExecute(
                                          dmaTransaction,
                                          dmaTransaction
                                          );

        if(!NT_SUCCESS(status)) {
            TraceEvents(
                        TRACE_LEVEL_ERROR,
                        DBG_WRITE, 
                        "WdfDmaTransactionExecute failed %X\n",
                        status
                        );
            break;
        }
    } while (FALSE);

    if(!NT_SUCCESS(status)){
 
        if(bCreated) {
            WdfObjectDelete(dmaTransaction);
        }
    }
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedwithlength.md">WdfDmaTransactionDmaCompletedWithLength</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>



<a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest.md">WdfDmaTransactionInitializeUsingRequest</a>



<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablersetmaximumscattergatherelements.md">WdfDmaEnablerSetMaximumScatterGatherElements</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitialize.md">WdfDmaTransactionInitialize</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompleted.md">WdfDmaTransactionDmaCompleted</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsetimmediateexecution.md">WdfDmaTransactionSetImmediateExecution</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal.md">WdfDmaTransactionDmaCompletedFinal</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionExecute method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

