---
UID: NC:wdfdmatransaction.EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE
title: EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE
author: windows-driver-content
description: A driver's EvtDmaTransactionDmaTransferComplete event callback function is called when the system-mode controller has completed the current DMA transfer.
old-location: wdf\evtdmatransactiondmatransfercomplete.htm
old-project: wdf
ms.assetid: C638A505-AAE1-48FC-B06B-F2F161ADC948
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdmatransactiondmatransfercomplete, EvtDmaTransactionDmaTransferComplete callback function, EvtDmaTransactionDmaTransferComplete, EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE, EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE, wdfdmatransaction/EvtDmaTransactionDmaTransferComplete, kmdf.evtdmatransactiondmatransfercomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	WdfDmaTransaction.h
apiname:
-	EvtDmaTransactionDmaTransferComplete
product: Windows
targetos: Windows
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---

# EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE callback


## -description


<p class="CCE_Message">[Applies to KMDF only]


   A driver's <i>EvtDmaTransactionDmaTransferComplete</i> event callback function is called when  the system-mode controller has completed the current DMA transfer.


## -prototype


````
EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE EvtDmaTransactionDmaTransferComplete;

void EvtDmaTransactionDmaTransferComplete(
  _In_ WDFDMATRANSACTION     Transaction,
  _In_ WDFDEVICE             Device,
  _In_ WDFCONTEXT            Context,
  _In_ WDF_DMA_DIRECTION     Direction,
  _In_ DMA_COMPLETION_STATUS Status
)
{ ... }
````


## -parameters




### -param Transaction [in]

A handle to a DMA transaction object representing the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transfer</a> that has just completed.


### -param Device [in]

A handle to the framework device object that the driver specified when it called <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>.


### -param Context [in]

The context pointer that the driver specified in a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsettransfercompletecallback.md">WdfDmaTransactionSetTransferCompleteCallback</a>.


### -param Direction [in]

A <a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_direction.md">WDF_DMA_DIRECTION</a>-typed value that specifies the direction of the completing DMA transfer operation.


### -param Status [in]

A <a href="..\wdm\ne-wdm-dma_completion_status.md">DMA_COMPLETION_STATUS</a>-typed value that specifies the status of the transfer.


## -returns


This callback function does not return a value.



## -remarks


The hardware for a bus-master DMA device typically issues an interrupt when a DMA transfer is complete. The driver then completes the DMA transfer in its <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a>  callback function.

However, the hardware for a system-mode DMA device does not always signal DMA transfer completion by issuing an interrupt. To receive notification of DMA transfer completion, a driver for a system-mode DMA device can instead register an <i>EvtDmaTransactionDmaTransferComplete</i> event callback function by calling <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsettransfercompletecallback.md">WdfDmaTransactionSetTransferCompleteCallback</a>.

The framework calls <i>EvtDmaTransactionDmaTransferComplete</i> after the system DMA controller has completed the transfer, once for each transfer in a transaction.

From within its <i>EvtDmaTransactionDmaTransferComplete</i> callback, the driver can call the following methods to notify the framework that the transfer has completed:
<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompleted.md">WdfDmaTransactionDmaCompleted</a><a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal.md">WdfDmaTransactionDmaCompletedFinal</a><a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedwithlength.md">WdfDmaTransactionDmaCompletedWithLength</a>The driver might not call one of the previous methods from <i>EvtDmaTransactionDmaTransferComplete</i>, opting instead to <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-timers">create a timer object</a> or schedule a DPC to complete the transfer later, as needed. After <b>WdfDmaTransactionDmaCompleted</b><i>Xxx</i> returns TRUE, indicating that no more transfers are needed to complete the DMA transaction, the driver can optionally call  <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionexecute.md">WdfDmaTransactionExecute</a> to initiate a subsequent transaction.

If the driver calls <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionstopsystemtransfer.md">WdfDmaTransactionStopSystemTransfer</a>, the framework calls <i>EvtDmaTransactionDmaTransferComplete</i> with a <i>Status</i> value of <b>DmaCancelled</b>.  In this case, the driver should call <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal.md">WdfDmaTransactionDmaCompletedFinal</a> from within <i>EvtDmaTransactionDmaTransferComplete</i>, and then can continue with request processing.

The driver must not manipulate the data buffers associated with the transaction until after <b>WdfDmaTransactionDmaCompleted</b><i>Xxx</i> has returned TRUE.

The driver can call <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionrelease.md">WdfDmaTransactionRelease</a> from within <i>EvtDmaTransactionDmaTransferComplete</i> if it needs to terminate the DMA transaction.

For more information about system-mode DMA, see <a href="https://msdn.microsoft.com/CCC77C15-69CA-44CB-8DEB-29F3EAEA44F6">Supporting System-Mode DMA</a>.



## -see-also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsettransfercompletecallback.md">WdfDmaTransactionSetTransferCompleteCallback</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

