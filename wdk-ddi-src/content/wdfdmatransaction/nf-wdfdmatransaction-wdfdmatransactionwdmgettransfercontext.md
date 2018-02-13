---
UID: NF:wdfdmatransaction.WdfDmaTransactionWdmGetTransferContext
title: WdfDmaTransactionWdmGetTransferContext function
author: windows-driver-content
description: The WdfDmaTransactionWdmGetTransferContext method retrieves the WDM transfer context that is associated with a DMA transaction.
old-location: wdf\wdfdmatransactionwdmgettransfercontext.htm
old-project: wdf
ms.assetid: EB156381-FC0E-40A3-A4AF-341AE70B97FF
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfdmatransaction/WdfDmaTransactionWdmGetTransferContext, kmdf.wdfdmatransactionwdmgettransfercontext, PFN_WDFDMATRANSACTIONWDMGETTRANSFERCONTEXT, wdf.wdfdmatransactionwdmgettransfercontext, WdfDmaTransactionWdmGetTransferContext method, WdfDmaTransactionWdmGetTransferContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	WdfDmaTransactionWdmGetTransferContext
product: Windows
targetos: Windows
req.typenames: "*PWDF_DMA_SYSTEM_PROFILE_CONFIG, WDF_DMA_SYSTEM_PROFILE_CONFIG"
req.product: Windows 10 or later.
---

# WdfDmaTransactionWdmGetTransferContext function


## -description


<p class="CCE_Message">[Applies to KMDF only]


   The <b>WdfDmaTransactionWdmGetTransferContext</b> method retrieves the WDM transfer context that is associated with a DMA transaction.


## -syntax


````
PVOID WdfDmaTransactionWdmGetTransferContext(
  _In_ WDFDMATRANSACTION DmaTransaction
);
````


## -parameters




### -param DmaTransaction [in]

A handle to an initialized DMA transaction object from which to retrieve the transfer context.


## -returns



A pointer to the DMA transfer context (PTRANSFER_CONTEXT) associated with the transaction.




## -remarks



The DMA transfer context for a transaction is allocated when the driver creates the transaction.

<b>WdfDmaTransactionWdmGetTransferContext</b> must be used with a DMA enabler that uses DMA version 3. To select version 3, set the <b>WdmDmaVersionOverride</b> member of <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a> to 3.

Your driver can use the DMA transfer context to call the following WDM DMA library routines directly:

<ul>
<li>
<a href="..\wdm\nc-wdm-pallocate_adapter_channel_ex.md">AllocateAdapterChannelEx</a>
</li>
<li>
<a href="..\wdm\nc-wdm-pcancel_adapter_channel.md">CancelAdapterChannel</a>
</li>
<li>
<a href="..\wdm\nc-wdm-pcancel_mapped_transfer.md">CancelMappedTransfer</a>
</li>
<li>
<a href="..\wdm\nc-wdm-pget_scatter_gather_list_ex.md">GetScatterGatherListEx</a>
</li>
<li>
<a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a>
</li>
</ul>
You must initialize the DMA transaction before calling <b>WdfDmaTransactionWdmGetTransferContext</b>.




## -see-also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionWdmGetTransferContext method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

