---
UID: NA:wdfdmatransaction
ms.assetid: 09e21580-15ec-3bb5-835c-b303aad3067a
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdfdmatransaction.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfdmatransaction.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WdfDmaTransactionAllocateResources function](nf-wdfdmatransaction-wdfdmatransactionallocateresources.md) | The WdfDmaTransactionAllocateResources method reserves a single-packet or system-mode DMA enabler for exclusive (and repeated) use with the specified transaction object. |
| [WdfDmaTransactionCancel function](nf-wdfdmatransaction-wdfdmatransactioncancel.md) | The WdfDmaTransactionCancel method attempts to cancel a DMA transaction that is waiting for the allocation of map registers. |
| [WdfDmaTransactionCreate function](nf-wdfdmatransaction-wdfdmatransactioncreate.md) | The WdfDmaTransactionCreate method creates a DMA transaction. |
| [WdfDmaTransactionDmaCompleted function](nf-wdfdmatransaction-wdfdmatransactiondmacompleted.md) | The WdfDmaTransactionDmaCompleted method notifies the framework that a device's DMA transfer operation is completed. |
| [WdfDmaTransactionDmaCompletedFinal function](nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal.md) | The WdfDmaTransactionDmaCompletedFinal method notifies the framework that a device's DMA transfer operation has completed with an underrun condition and supplies the length of the completed transfer. |
| [WdfDmaTransactionDmaCompletedWithLength function](nf-wdfdmatransaction-wdfdmatransactiondmacompletedwithlength.md) | The WdfDmaTransactionDmaCompletedWithLength method notifies the framework that a device's DMA transfer operation is complete and supplies the length of the completed transfer. |
| [WdfDmaTransactionExecute function](nf-wdfdmatransaction-wdfdmatransactionexecute.md) | The WdfDmaTransactionExecute method begins the execution of a specified DMA transaction. |
| [WdfDmaTransactionFreeResources function](nf-wdfdmatransaction-wdfdmatransactionfreeresources.md) | The WdfDmaTransactionFreeResources method releases DMA resources that the driver previously allocated by calling WdfDmaTransactionAllocateResources. |
| [WdfDmaTransactionGetBytesTransferred function](nf-wdfdmatransaction-wdfdmatransactiongetbytestransferred.md) | The WdfDmaTransactionGetBytesTransferred method returns the total number of bytes that have been transferred for a specified DMA transaction. |
| [WdfDmaTransactionGetCurrentDmaTransferLength function](nf-wdfdmatransaction-wdfdmatransactiongetcurrentdmatransferlength.md) | The WdfDmaTransactionGetCurrentDmaTransferLength method returns the size of the current DMA transfer. |
| [WdfDmaTransactionGetDevice function](nf-wdfdmatransaction-wdfdmatransactiongetdevice.md) | The WdfDmaTransactionGetDevice method returns a handle to the framework device object that is associated with a specified DMA transaction. |
| [WdfDmaTransactionGetRequest function](nf-wdfdmatransaction-wdfdmatransactiongetrequest.md) | The WdfDmaTransactionGetRequest method retrieves a handle to the framework request object that is associated with a specified DMA transaction. |
| [WdfDmaTransactionGetTransferInfo function](nf-wdfdmatransaction-wdfdmatransactiongettransferinfo.md) | The WdfDmaTransactionGetTransferInfo method returns the number of map registers and scatter/gather list entries required for an initialized DMA transaction. |
| [WdfDmaTransactionInitialize function](nf-wdfdmatransaction-wdfdmatransactioninitialize.md) | The WdfDmaTransactionInitialize method initializes a specified DMA transaction. |
| [WdfDmaTransactionInitializeUsingOffset function](nf-wdfdmatransaction-wdfdmatransactioninitializeusingoffset.md) | The WdfDmaTransactionInitializeUsingOffset method initializes a specified DMA transaction by using a byte offset into an MDL chain. |
| [WdfDmaTransactionInitializeUsingRequest function](nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest.md) | The WdfDmaTransactionInitializeUsingRequest method initializes a specified DMA transaction by using the parameters of a specified I/O request. |
| [WdfDmaTransactionRelease function](nf-wdfdmatransaction-wdfdmatransactionrelease.md) | The WdfDmaTransactionRelease method terminates a specified DMA transaction without deleting the associated DMA transaction object. |
| [WdfDmaTransactionSetChannelConfigurationCallback function](nf-wdfdmatransaction-wdfdmatransactionsetchannelconfigurationcallback.md) | The WdfDmaTransactionSetChannelConfigurationCallback method registers a channel configuration event callback function for a system-mode DMA transaction. |
| [WdfDmaTransactionSetDeviceAddressOffset function](nf-wdfdmatransaction-wdfdmatransactionsetdeviceaddressoffset.md) | The WdfDmaTransactionSetDeviceAddressOffset method specifies the offset of the register that the system DMA controller will access when performing the DMA operation. |
| [WdfDmaTransactionSetImmediateExecution function](nf-wdfdmatransaction-wdfdmatransactionsetimmediateexecution.md) | The WdfDmaTransactionSetImmediateExecution method marks the specified DMA transaction so that calls to WdfDmaTransactionExecute and WdfDmaTransactionAllocateResources initiate the transaction immediately or fail. |
| [WdfDmaTransactionSetMaximumLength function](nf-wdfdmatransaction-wdfdmatransactionsetmaximumlength.md) | The WdfDmaTransactionSetMaximumLength method sets the maximum length for the DMA transfers that are associated with a specified DMA transaction. |
| [WdfDmaTransactionSetSingleTransferRequirement function](nf-wdfdmatransaction-wdfdmatransactionsetsingletransferrequirement.md) | The WdfDmaTransactionSetSingleTransferRequirement method specifies that a DMA transaction must complete in a single transfer. |
| [WdfDmaTransactionSetTransferCompleteCallback function](nf-wdfdmatransaction-wdfdmatransactionsettransfercompletecallback.md) | The WdfDmaTransactionSetTransferCompleteCallback method registers a transfer completion event callback function for a system-mode DMA transaction. |
| [WdfDmaTransactionStopSystemTransfer function](nf-wdfdmatransaction-wdfdmatransactionstopsystemtransfer.md) | The WdfDmaTransactionStopSystemTransfer method attempts to stop a system-mode DMA transfer after the framework has called EvtProgramDma. |
| [WdfDmaTransactionWdmGetTransferContext function](nf-wdfdmatransaction-wdfdmatransactionwdmgettransfercontext.md) | The WdfDmaTransactionWdmGetTransferContext method retrieves the WDM transfer context that is associated with a DMA transaction. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL callback](nc-wdfdmatransaction-evt_wdf_dma_transaction_configure_dma_channel.md) | A driver's EvtDmaTransactionConfigureDmaChannel event callback function configures the DMA adapter for a system-mode DMA enabler. |
| [EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE callback](nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete.md) | A driver's EvtDmaTransactionDmaTransferComplete event callback function is called when the system-mode controller has completed the current DMA transfer. |
| [EVT_WDF_RESERVE_DMA callback](nc-wdfdmatransaction-evt_wdf_reserve_dma.md) | The EvtReserveDma event callback function is called when the framework has reserved resources to execute and release a transaction. Reserved resources include map registers and the WDM DMA adapter's lock. |
