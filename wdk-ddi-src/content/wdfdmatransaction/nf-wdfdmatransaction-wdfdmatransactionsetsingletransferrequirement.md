---
UID: NF:wdfdmatransaction.WdfDmaTransactionSetSingleTransferRequirement
title: WdfDmaTransactionSetSingleTransferRequirement function (wdfdmatransaction.h)
description: The WdfDmaTransactionSetSingleTransferRequirement method specifies that a DMA transaction must complete in a single transfer.
old-location: wdf\wdfdmatransactionsetsingletransferrequirement.htm
tech.root: wdf
ms.assetid: 988c7e70-3b2a-4a0f-91cf-dfab3ea07f05
ms.date: 02/26/2018
ms.keywords: WdfDmaTransactionSetSingleTransferRequirement, WdfDmaTransactionSetSingleTransferRequirement method, wdf.wdfdmatransactionsetsingletransferrequirement, wdfdmatransaction/WdfDmaTransactionSetSingleTransferRequirement
f1_keywords:
 - "wdfdmatransaction/WdfDmaTransactionSetSingleTransferRequirement"
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.19
req.umdf-ver: 
req.ddi-compliance: 
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
- WdfDmaTransactionSetSingleTransferRequirement
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionSetSingleTransferRequirement function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaTransactionSetSingleTransferRequirement</b> method specifies that a DMA transaction must complete in a single transfer.


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>.


### -param RequireSingleTransfer [in]

A Boolean value that, if <b>TRUE</b>, specifies that the DMA transaction requires a single transfer.


## -remarks



This method requests a single transfer for a single transaction only. When the transaction object is recycled with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionrelease">WdfDmaTransactionRelease</a> and reinitialized, this setting resets, similar to other transaction-level properties such as immediate execution and maximum transfer length.

To request single transfer for all DMA transactions created with a given DMA enabler, specify  <b>WDF_DMA_ENABLER_CONFIG_REQUIRE_SINGLE_TRANSFER</b> in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ne-wdfdmaenabler-_wdf_dma_enabler_config_flags">WDF_DMA_ENABLER_CONFIG_FLAGS</a> when calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>. This is equivalent to calling <b>WdfDmaTransactionSetSingleTransferRequirement</b> for each transaction object created with the DMA enabler.

The driver calls <b>WdfDmaTransactionSetSingleTransferRequirement</b> after creating or recycling the transaction object, but before initializing or executing it.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/">Using Single Transfer DMA</a>.

<b>WdfDmaTransactionSetSingleTransferRequirement</b> requires DMA version 3.
 To select DMA version 3, set the <b>WdmDmaVersionOverride</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> to 3.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitialize">WdfDmaTransactionInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest">WdfDmaTransactionInitializeUsingRequest</a>
 

 

