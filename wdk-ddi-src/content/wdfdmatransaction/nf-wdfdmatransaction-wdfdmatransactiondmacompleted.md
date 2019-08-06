---
UID: NF:wdfdmatransaction.WdfDmaTransactionDmaCompleted
title: WdfDmaTransactionDmaCompleted function (wdfdmatransaction.h)
description: The WdfDmaTransactionDmaCompleted method notifies the framework that a device's DMA transfer operation is completed.
old-location: wdf\wdfdmatransactiondmacompleted.htm
tech.root: wdf
ms.assetid: 83c1c4cb-b28b-4980-92fb-a1a49d95406e
ms.date: 02/26/2018
ms.keywords: DFDmaObjectRef_d7fd815f-7c21-4b84-b4f2-0dcc13cf068a.xml, WdfDmaTransactionDmaCompleted, WdfDmaTransactionDmaCompleted method, kmdf.wdfdmatransactiondmacompleted, wdf.wdfdmatransactiondmacompleted, wdfdmatransaction/WdfDmaTransactionDmaCompleted
ms.topic: function
f1_keywords:
 - "wdfdmatransaction/WdfDmaTransactionDmaCompleted"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDmaTransactionDmaCompleted
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionDmaCompleted function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaTransactionDmaCompleted</b> method notifies the framework that a device's DMA transfer operation is completed.  


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>.


### -param Status [out]

A pointer to a location that receives the status of the DMA transfer. For more information, see the following Remarks section.


## -returns



<b>WdfDmaTransactionDmaCompleted</b> returns <b>FALSE</b> and <i>Status</i> receives STATUS_MORE_PROCESSING_REQUIRED if additional transfers are needed to complete the DMA transaction. The method returns <b>TRUE</b> if no additional transfers are required. 

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Framework-based drivers must call one of the following methods whenever a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transfer</a> is complete:

<ul>
<li>
<b>WdfDmaTransactionDmaCompleted</b>

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompletedwithlength">WdfDmaTransactionDmaCompletedWithLength</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal">WdfDmaTransactionDmaCompletedFinal</a>


</li>
</ul>
Typically, drivers call these methods from within an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> event callback function, after a device interrupt indicates the completion of a DMA transfer operation. A driver for a system-mode DMA device might call these methods from within an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete">EvtDmaTransactionDmaTransferComplete</a> event callback function.

The framework might divide a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transaction</a> into several DMA transfer operations. Therefore, the driver must examine the method's return value to determine if additional transfers are required. 

If the method returns <b>FALSE</b>, the <i>Status</i> location receives STATUS_MORE_PROCESSING_REQUIRED and additional DMA operations are required to complete the transaction. Typically, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> event callback function does nothing else at this point. Instead, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a> event callback function, so the callback function can begin the next transfer. 

If the method returns <b>TRUE</b>, no more transfers will occur for the specified transaction. In this case, a <i>Status</i> value of STATUS_SUCCESS means that the framework did not encounter any errors and the DMA transaction is complete. 

If the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionstopsystemtransfer">WdfDmaTransactionStopSystemTransfer</a> before calling <b>WdfDmaTransactionDmaCompleted</b>, <b>WdfDmaTransactionDmaCompleted</b> returns <b>TRUE</b> and a <i>Status</i> value of <b>STATUS_CANCELLED</b>.

For transactions that were set for <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/">single transfer</a>, <b>WdfDmaTransactionDmaCompleted</b> returns <b>TRUE</b> and a <i>Status</i> value of <b>STATUS_WDF_TOO_MANY_TRANSFERS</b> if the hardware fails to complete the transaction in a single transfer, even though initialization succeeded.
 	This could happen for hardware that reports residual transfers for each DMA operation. For example, the driver programs the device to write 64KB, but the device writes only 60KB.
   In this case, the driver might repeat the DMA operation or reset the device.

Any other value for <i>Status</i> means that the framework detected an error and the DMA transaction might not have been completed.

When <b>WdfDmaTransactionDmaCompleted</b> returns <b>TRUE</b>, the driver typically does the following:

<ul>
<li>
Calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nf-wdfobject-wdfobjectdelete">WdfObjectDelete</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionrelease">WdfDmaTransactionRelease</a> to delete or reuse the transaction object, respectively.

</li>
<li>
Completes the I/O request, if the DMA transaction is associated with an I/O request. (Drivers complete requests by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcompletewithinformation">WdfRequestCompleteWithInformation</a>.)

</li>
</ul>
For more information about completing DMA transfers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-a-dma-transfer">Completing a DMA Transfer</a>.


#### Examples

The following code example is from the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">AMCC5933</a> sample driver. This example shows an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback function. The example notifies the framework that a DMA transfer has completed. If the framework indicates that this transfer is the last one for the DMA transaction, the code deletes the DMA transaction object and completes the associated I/O request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
AmccPciEvtInterruptDpc(
    IN WDFINTERRUPT  WdfInterrupt,
    IN WDFOBJECT  WdfDevice
    )
{
    PAMCC_DEVICE_EXTENSION  devExt;
    WDFREQUEST  request;
    REQUEST_CONTEXT  *transfer;
    NTSTATUS  status;
    size_t  transferred;
    BOOLEAN  transactionComplete;

    UNREFERENCED_PARAMETER( WdfInterrupt );

    //
    // Retrieve request and transfer.
    //
    devExt = AmccPciGetDevExt(WdfDevice);
    request  = devExt->CurrentRequest;
    transfer = GetRequestContext(request);

    //
    // Check to see if the request has been canceled. 
    //
    if (WdfRequestIsCanceled(request)) {
        TraceEvents(
                    TRACE_LEVEL_ERROR,
                    AMCC_TRACE_IO,
                    "Aborted DMA transaction 0x%p",
                    request
                    );
        WdfObjectDelete( transfer->DmaTransaction );
        devExt->CurrentRequest = NULL;
        WdfRequestComplete(
                           request,
                           STATUS_CANCELLED
                           );
        return;
    }
 
    //
    // Notify the framework that a DMA transfer has completed.
    //
    transactionComplete = WdfDmaTransactionDmaCompleted(
                                                    transfer->DmaTransaction,
                                                    &status
                                                    );
    if (transactionComplete) {
        ASSERT(status != STATUS_MORE_PROCESSING_REQUIRED);

        //
        // No more data. The request is complete.
        //
        TraceEvents(
                    TRACE_LEVEL_INFORMATION,
                    AMCC_TRACE_IO,
                    "Request %p completed: status %X",  
                    request,
                    status
                    );

        //
        // Get the byte count.
        //
        transferred =
                WdfDmaTransactionGetBytesTransferred(transfer->DmaTransaction);

        TraceEvents(
                    TRACE_LEVEL_INFORMATION,
                    AMCC_TRACE_IO,
                    "Bytes transferred %d",
                    (int) transferred
                    );

        //
        // Delete this DmaTransaction object.
        //
        WdfObjectDelete(transfer->DmaTransaction);

        //
        // Clean up the device context for this request.
        //
        devExt->CurrentRequest = NULL;

        //
        // Complete this I/O request.
        //
        WdfRequestCompleteWithInformation(
                                          request, 
                                          status,
                                          (NT_SUCCESS(status)) ? transferred : 0
                                          );
    }
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal">WdfDmaTransactionDmaCompletedFinal</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompletedwithlength">WdfDmaTransactionDmaCompletedWithLength</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionrelease">WdfDmaTransactionRelease</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nf-wdfobject-wdfobjectdelete">WdfObjectDelete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcompletewithinformation">WdfRequestCompleteWithInformation</a>
 

 

