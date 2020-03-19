---
UID: NF:wdfdmatransaction.WdfDmaTransactionExecute
title: WdfDmaTransactionExecute function (wdfdmatransaction.h)
description: The WdfDmaTransactionExecute method begins the execution of a specified DMA transaction.
old-location: wdf\wdfdmatransactionexecute.htm
tech.root: wdf
ms.assetid: 8f52557f-b65d-479d-aab4-1e4f7298c8f9
ms.date: 02/26/2018
keywords: ["WdfDmaTransactionExecute function"]
ms.keywords: DFDmaObjectRef_012a66e9-0ed7-458f-9068-c7d2ce58d86a.xml, WdfDmaTransactionExecute, WdfDmaTransactionExecute method, kmdf.wdfdmatransactionexecute, wdf.wdfdmatransactionexecute, wdfdmatransaction/WdfDmaTransactionExecute
f1_keywords:
 - "wdfdmatransaction/WdfDmaTransactionExecute"
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
- WdfDmaTransactionExecute
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionExecute function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaTransactionExecute</b> method begins the execution of a specified DMA transaction. 


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>.


### -param Context [in, optional]

Driver-defined context information. The framework passes the value specified for <i>Context</i>, which can be a pointer, to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a> event callback function. This parameter is optional and can be <b>NULL</b>.


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
The driver previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsetimmediateexecution">WdfDmaTransactionSetImmediateExecution</a> and the resources needed for the request are unavailable.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionexecute">WdfDmaTransactionExecute</a> was not preceded by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitialize">WdfDmaTransactionInitialize</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest">WdfDmaTransactionInitializeUsingRequest</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_BUSY</b></dt>
</dl>
</td>
<td width="60%">
The device performs single-packet transfers, and the driver called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionexecute">WdfDmaTransactionExecute</a> while another transaction was executing.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_TOO_FRAGMENTED</b></dt>
</dl>
</td>
<td width="60%">
The number of scatter/gather elements that the operating system needed to handle the specified transfer size was greater than the value that the driver's call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablersetmaximumscattergatherelements">WdfDmaEnablerSetMaximumScatterGatherElements</a> specified. For more information, see the following Remarks section.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfDmaTransactionExecute</b> method initializes a transaction's scatter/gather list for the first <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transfer</a> that is associated with the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transaction</a>. (For single-packet transfers, the scatter/gather list contains a single element.) Then, the method calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a> event callback function, and the callback function can program the device to begin the transfer. 

Framework-based drivers typically call <b>WdfDmaTransactionExecute</b> from within an <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">I/O queue event callback function</a>. 

After a driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitialize">WdfDmaTransactionInitialize</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest">WdfDmaTransactionInitializeUsingRequest</a> to initialize a DMA transaction, the driver must call <b>WdfDmaTransactionExecute</b> only once before <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-a-dma-transaction">completing the DMA transaction</a>. 


          If <b>WdfDmaTransactionInitialize<i>Xxx</i></b> returns success but <b>WdfDmaTransactionExecute</b> returns an error value, your driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionrelease">WdfDmaTransactionRelease</a>.

In framework versions prior to 1.11, if the device performs single-packet transfers, the operating system can execute only one DMA transaction at a time. In this case, <b>WdfDmaTransactionExecute</b> returns STATUS_WDF_BUSY if another transaction is executing.

In framework versions 1.11 and later, if the driver uses DMA version 3 to perform single-packet transfers, the operating system can store multiple DMA transactions in an internal queue. In this case, the driver can call <b>WdfDmaTransactionExecute</b> while another transaction is executing. To select DMA version 3, set the <b>WdmDmaVersionOverride</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> to 3.

If the device performs scatter/gather transfers, the operating system can execute multiple DMA transactions simultaneously. In this case, the driver can call <b>WdfDmaTransactionExecute</b> while another transaction is executing.

If the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompletedwithlength">WdfDmaTransactionDmaCompletedWithLength</a> to report a partial transfer, and if the driver had specified the DMA transaction's data buffer by using MDLs that it chained together (using the <b>Next</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a> structure), <b>WdfDmaTransactionExecute</b> can return STATUS_WDF_TOO_FRAGMENTED because the framework might recalculate the number and size of fragments and might exceed the number of allowed fragments.

The <b>WdfDmaTransactionExecute</b> returns STATUS_SUCCESS if the transaction was successfully started. To determine if the framework successfully sent all of the transaction's transfers to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a> callback function, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompleted">WdfDmaTransactionDmaCompleted</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompletedwithlength">WdfDmaTransactionDmaCompletedWithLength</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal">WdfDmaTransactionDmaCompletedFinal</a>.

If the value that the <i>Context</i> parameter supplies is a pointer or handle, the memory that it references must be accessible in the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a> event callback function at IRQL = DISPATCH_LEVEL. You can use <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-context-space">framework object context</a> to meet this requirement.

The driver can call <b>WdfDmaTransactionExecute</b> in a non-blocking manner if it has previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsetimmediateexecution">WdfDmaTransactionSetImmediateExecution</a>.

For more information about DMA transactions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/starting-a-dma-transaction">Starting a DMA Transaction</a>.


#### Examples

The following code example is from the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">PCIDRV</a> sample driver. This example creates and initializes a DMA transfer and begins its execution.

```cpp
NTSTATUS
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
                                         FdoData->WdfDmaEnabler,
                                         WDF_NO_OBJECT_ATTRIBUTES,
                                         &dmaTransaction
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
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablersetmaximumscattergatherelements">WdfDmaEnablerSetMaximumScatterGatherElements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompleted">WdfDmaTransactionDmaCompleted</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal">WdfDmaTransactionDmaCompletedFinal</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompletedwithlength">WdfDmaTransactionDmaCompletedWithLength</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitialize">WdfDmaTransactionInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest">WdfDmaTransactionInitializeUsingRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsetimmediateexecution">WdfDmaTransactionSetImmediateExecution</a>
 

 

