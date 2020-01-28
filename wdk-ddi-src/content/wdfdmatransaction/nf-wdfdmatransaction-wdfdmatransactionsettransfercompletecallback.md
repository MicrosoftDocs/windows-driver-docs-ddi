---
UID: NF:wdfdmatransaction.WdfDmaTransactionSetTransferCompleteCallback
title: WdfDmaTransactionSetTransferCompleteCallback function (wdfdmatransaction.h)
description: The WdfDmaTransactionSetTransferCompleteCallback method registers a transfer completion event callback function for a system-mode DMA transaction.
old-location: wdf\wdfdmatransactionsettransfercompletecallback.htm
tech.root: wdf
ms.assetid: B97FF6B1-BFCB-4293-B2F0-EE08E12CFCFF
ms.date: 02/26/2018
ms.keywords: WdfDmaTransactionSetTransferCompleteCallback, WdfDmaTransactionSetTransferCompleteCallback method, kmdf.wdfdmatransactionsettransfercompletecallback, wdf.wdfdmatransactionsettransfercompletecallback, wdfdmatransaction/WdfDmaTransactionSetTransferCompleteCallback
f1_keywords:
 - "wdfdmatransaction/WdfDmaTransactionSetTransferCompleteCallback"
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: DriverCreate
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
- WdfDmaTransactionSetTransferCompleteCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionSetTransferCompleteCallback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   The <b>WdfDmaTransactionSetTransferCompleteCallback</b> method registers a transfer completion event callback function for a system-mode DMA transaction.


## -parameters




### -param DmaTransaction [in]

A handle to an initialized DMA transaction object for which to set or clear the transfer completion callback.


### -param DmaCompletionRoutine [in, optional]

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete">EvtDmaTransactionDmaTransferComplete</a> event callback function, or NULL to clear a previously set callback function.


### -param DmaCompletionContext [in, optional]

A pointer to a buffer containing the driver-specified context to be provided to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete">EvtDmaTransactionDmaTransferComplete</a> event callback function, or NULL.


## -remarks



The driver calls this method to set a completion routine that the framework calls after the system DMA controller completes a transfer.  The framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete">EvtDmaTransactionDmaTransferComplete</a> callback once for each transfer in the transaction.

Typically from within an <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">I/O queue event callback function</a>, a driver performs the following steps, in this order:

<ol>
<li>Calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest">WdfDmaTransactionInitializeUsingRequest</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitialize">WdfDmaTransactionInitialize</a>, or  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitializeusingoffset">WdfDmaTransactionInitializeUsingOffset</a>  to initialize the transaction object.</li>
<li>Calls <b>WdfDmaTransactionSetTransferCompleteCallback</b> on the transaction object.</li>
<li>Calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionexecute">WdfDmaTransactionExecute</a>.</li>
</ol>
If the driver has specified an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete">EvtDmaTransactionDmaTransferComplete</a> event callback function by calling <b>WdfDmaTransactionSetTransferCompleteCallback</b> and the driver subsequently calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionrelease">WdfDmaTransactionRelease</a>, the callback is cleared.

<b>WdfDmaTransactionSetTransferCompleteCallback</b> can only be used with a DMA enabler that specifies a system-mode DMA profile.

If your driver calls this method on an operating system earlier than Windows 8, <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-kmdf-verifier">the framework's verifier</a> reports an error.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete">EvtDmaTransactionDmaTransferComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionrelease">WdfDmaTransactionRelease</a>
 

 

