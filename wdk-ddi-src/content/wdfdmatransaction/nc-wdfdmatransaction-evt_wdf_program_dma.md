---
UID: NC:wdfdmatransaction.EVT_WDF_PROGRAM_DMA
title: EVT_WDF_PROGRAM_DMA (wdfdmatransaction.h)
description: A framework-based driver's EvtProgramDma event callback function programs a specified device to perform a DMA transfer operation.
old-location: wdf\evtprogramdma.htm
tech.root: wdf
ms.assetid: c01b94b2-aabf-47dd-952a-06e481579614
ms.date: 02/26/2018
keywords: ["EVT_WDF_PROGRAM_DMA callback function"]
ms.keywords: DFDmaObjectRef_972816f8-bfd1-487d-8ac4-7ef75dcdfa97.xml, EVT_WDF_PROGRAM_DMA, EVT_WDF_PROGRAM_DMA callback, EvtProgramDma, EvtProgramDma callback function, kmdf.evtprogramdma, wdf.evtprogramdma, wdfdmatransaction/EvtProgramDma
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
 - EVT_WDF_PROGRAM_DMA
 - wdfdmatransaction/EVT_WDF_PROGRAM_DMA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wdfdmatransaction.h
api_name:
 - EvtProgramDma
---

# EVT_WDF_PROGRAM_DMA callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A framework-based driver's <i>EvtProgramDma</i> event callback function programs a specified device to perform a DMA transfer operation.

## -parameters

### -param Transaction 

[in]
A handle to the DMA transaction object that represents the current DMA transaction.

### -param Device 

[in]
A handle to a framework device object.

### -param Context 

[in]
The context pointer that the driver specified in a previous call to <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionexecute">WdfDmaTransactionExecute</a>.

### -param Direction 

[in]
A <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/ne-wdfdmaenabler-_wdf_dma_direction">WDF_DMA_DIRECTION</a>-typed value that specifies the direction of the DMA transfer operation.

### -param SgList 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a> structure.

## -returns

The <i>EvtProgramDma</i> callback function must return <b>TRUE</b> if it successfully starts the DMA transfer operation. Otherwise, this callback function must return <b>FALSE</b>. However, the framework currently ignores the return value.

## -remarks

Drivers register an <i>EvtProgramDma</i> event callback function by calling <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest">WdfDmaTransactionInitializeUsingRequest</a> or <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitialize">WdfDmaTransactionInitialize</a>.

The framework calls a driver's <i>EvtProgramDma</i> event callback function when a <a href="/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transfer</a> is available. The callback function must program the hardware to start the transfer.

The driver must not manipulate the data buffers associated with the transaction until after <b>WdfDmaTransactionDmaCompleted</b><i>Xxx</i> has returned TRUE.

For single packet transfers, the scatter/gather list that the <i>SgList</i> parameter points to contains a single element.

For more information about this callback function, see <a href="/windows-hardware/drivers/wdf/programming-dma-hardware">Programming DMA Hardware</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionexecute">WdfDmaTransactionExecute</a>



<a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitialize">WdfDmaTransactionInitialize</a>



<a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest">WdfDmaTransactionInitializeUsingRequest</a>