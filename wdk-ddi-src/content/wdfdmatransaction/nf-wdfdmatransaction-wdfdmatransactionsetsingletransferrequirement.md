---
UID: NF:wdfdmatransaction.WdfDmaTransactionSetSingleTransferRequirement
title: WdfDmaTransactionSetSingleTransferRequirement function
author: windows-driver-content
description: The WdfDmaTransactionSetSingleTransferRequirement method specifies that a DMA transaction must complete in a single transfer.
old-location: wdf\wdfdmatransactionsetsingletransferrequirement.htm
old-project: wdf
ms.assetid: 988c7e70-3b2a-4a0f-91cf-dfab3ea07f05
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfDmaTransactionSetSingleTransferRequirement, WdfDmaTransactionSetSingleTransferRequirement method, wdf.wdfdmatransactionsetsingletransferrequirement, wdfdmatransaction/WdfDmaTransactionSetSingleTransferRequirement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDmaTransactionSetSingleTransferRequirement
product: Windows
targetos: Windows
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---

# WdfDmaTransactionSetSingleTransferRequirement function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionSetSingleTransferRequirement</b> method specifies that a DMA transaction must complete in a single transfer.


## -syntax


````
void WdfDmaTransactionSetSingleTransferRequirement(
  _In_ WDFDMATRANSACTION DmaTransaction,
  _In_ BOOLEAN           RequireSingleTransfer
);
````


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>.


### -param RequireSingleTransfer [in]

A Boolean value that, if <b>TRUE</b>, specifies that the DMA transaction requires a single transfer.


## -returns



This method does not return a value.




## -remarks



This method requests a single transfer for a single transaction only. When the transaction object is recycled with <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionrelease.md">WdfDmaTransactionRelease</a> and reinitialized, this setting resets, similar to other transaction-level properties such as immediate execution and maximum transfer length.

To request single transfer for all DMA transactions created with a given DMA enabler, specify  <b>WDF_DMA_ENABLER_CONFIG_REQUIRE_SINGLE_TRANSFER</b> in <a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_enabler_config_flags.md">WDF_DMA_ENABLER_CONFIG_FLAGS</a> when calling <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>. This is equivalent to calling <b>WdfDmaTransactionSetSingleTransferRequirement</b> for each transaction object created with the DMA enabler.

The driver calls <b>WdfDmaTransactionSetSingleTransferRequirement</b> after creating or recycling the transaction object, but before initializing or executing it.  For more info, see <a href="https://msdn.microsoft.com/windows/hardware/drivers/wdf/">Using Single Transfer DMA</a>.

<b>WdfDmaTransactionSetSingleTransferRequirement</b> requires DMA version 3.
 To select DMA version 3, set the <b>WdmDmaVersionOverride</b> member of <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a> to 3.




## -see-also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitialize.md">WdfDmaTransactionInitialize</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest.md">WdfDmaTransactionInitializeUsingRequest</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionSetSingleTransferRequirement method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

