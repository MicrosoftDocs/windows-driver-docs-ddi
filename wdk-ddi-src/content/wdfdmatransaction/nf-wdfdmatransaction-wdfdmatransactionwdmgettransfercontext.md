---
UID: NF:wdfdmatransaction.WdfDmaTransactionWdmGetTransferContext
title: WdfDmaTransactionWdmGetTransferContext function (wdfdmatransaction.h)
description: The WdfDmaTransactionWdmGetTransferContext method retrieves the WDM transfer context that is associated with a DMA transaction.
old-location: wdf\wdfdmatransactionwdmgettransfercontext.htm
tech.root: wdf
ms.assetid: EB156381-FC0E-40A3-A4AF-341AE70B97FF
ms.date: 02/26/2018
ms.keywords: WdfDmaTransactionWdmGetTransferContext, WdfDmaTransactionWdmGetTransferContext method, kmdf.wdfdmatransactionwdmgettransfercontext, wdf.wdfdmatransactionwdmgettransfercontext, wdfdmatransaction/WdfDmaTransactionWdmGetTransferContext
ms.topic: function
f1_keywords:
 - "wdfdmatransaction/WdfDmaTransactionWdmGetTransferContext"
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
- WdfDmaTransactionWdmGetTransferContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionWdmGetTransferContext function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   The <b>WdfDmaTransactionWdmGetTransferContext</b> method retrieves the WDM transfer context that is associated with a DMA transaction.


## -parameters




### -param DmaTransaction [in]

A handle to an initialized DMA transaction object from which to retrieve the transfer context.


## -returns



A pointer to the DMA transfer context (PTRANSFER_CONTEXT) associated with the transaction.




## -remarks



The DMA transfer context for a transaction is allocated when the driver creates the transaction.

<b>WdfDmaTransactionWdmGetTransferContext</b> must be used with a DMA enabler that uses DMA version 3. To select version 3, set the <b>WdmDmaVersionOverride</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> to 3.

Your driver can use the DMA transfer context to call the following WDM DMA library routines directly:

<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pallocate_adapter_channel_ex">AllocateAdapterChannelEx</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pcancel_adapter_channel">CancelAdapterChannel</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pcancel_mapped_transfer">CancelMappedTransfer</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pget_scatter_gather_list_ex">GetScatterGatherListEx</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pbuild_scatter_gather_list_ex">BuildScatterGatherListEx</a>
</li>
</ul>
You must initialize the DMA transaction before calling <b>WdfDmaTransactionWdmGetTransferContext</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>
 

 

