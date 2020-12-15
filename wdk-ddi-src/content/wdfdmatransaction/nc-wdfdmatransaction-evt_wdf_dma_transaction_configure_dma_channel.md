---
UID: NC:wdfdmatransaction.EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL
title: EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL (wdfdmatransaction.h)
description: A driver's EvtDmaTransactionConfigureDmaChannel event callback function configures the DMA adapter for a system-mode DMA enabler.
old-location: wdf\evtdmatransactionconfiguredmachannel.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL callback function"]
ms.keywords: EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL, EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL callback, EvtDmaTransactionConfigureDmaChannel, EvtDmaTransactionConfigureDmaChannel callback function, kmdf.evtdmatransactionconfiguredmachannel, wdf.evtdmatransactionconfiguredmachannel, wdfdmatransaction/EvtDmaTransactionConfigureDmaChannel
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL
 - wdfdmatransaction/EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - WdfDmaTransaction.h
api_name:
 - EvtDmaTransactionConfigureDmaChannel
---

# EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>


   A driver's <i>EvtDmaTransactionConfigureDmaChannel</i> event callback function configures the DMA adapter for a system-mode DMA enabler.

## -parameters

### -param DmaTransaction 

[in]
A handle to a DMA transaction object representing the transaction that is being executed.

### -param Device 

[in]
A handle to the framework device object that the driver specified when it called <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>.

### -param Context 

[in]
The context pointer that the driver specified in a previous call to <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsetchannelconfigurationcallback">WdfDmaTransactionSetChannelConfigurationCallback</a>.

### -param Mdl 

[in, optional]
A pointer to a single memory descriptor list (MDL) or MDL chain that describes the buffer associated with the current transfer, or NULL if the last transfer has been completed and the adapter is being freed.

### -param Offset 

[in]
A byte offset into the buffer specified in the <i>Mdl</i> parameter where the current transfer starts.

### -param Length 

[in]
The number of bytes being transferred in the current transfer.

## -returns

The <i>EvtDmaTransactionConfigureDmaChannel</i> callback function returns TRUE if it successfully configures the DMA channel. If this callback function returns FALSE, the framework stops the transaction and does not call <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a>.

## -remarks

Drivers register an <i>EvtDmaTransactionConfigureDmaChannel</i> event callback function by calling <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsetchannelconfigurationcallback">WdfDmaTransactionSetChannelConfigurationCallback</a>.

The framework calls <i>EvtDmaTransactionConfigureDmaChannel</i> once for each system-profile DMA transfer in the transaction, after allocating the adapter channel but before mapping the transfer and calling <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a>.

The driver can use the <i>EvtDmaTransactionConfigureDmaChannel</i> callback to set any custom programming for the DMA adapter before mapping a transfer.



If the driver experiences an error while configuring the channel, it can stop the DMA transfer by calling <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal">WdfDmaTransactionDmaCompletedFinal</a> and, if necessary, completing the request. The driver should then return FALSE from this callback function.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal">WdfDmaTransactionDmaCompletedFinal</a>



<a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsetchannelconfigurationcallback">WdfDmaTransactionSetChannelConfigurationCallback</a>
