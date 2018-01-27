---
UID: NC:wdfdmatransaction.EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL
title: EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL
author: windows-driver-content
description: A driver's EvtDmaTransactionConfigureDmaChannel event callback function configures the DMA adapter for a system-mode DMA enabler.
old-location: wdf\evtdmatransactionconfiguredmachannel.htm
old-project: wdf
ms.assetid: 405D1D3F-FC01-4223-8E28-B3FD3F0516F7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdmatransactionconfiguredmachannel, EvtDmaTransactionConfigureDmaChannel callback function, EvtDmaTransactionConfigureDmaChannel, EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL, EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL, wdfdmatransaction/EvtDmaTransactionConfigureDmaChannel, kmdf.evtdmatransactionconfiguredmachannel
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
-	EvtDmaTransactionConfigureDmaChannel
product: Windows
targetos: Windows
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---

# EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL callback


## -description


<p class="CCE_Message">[Applies to KMDF only]


   A driver's <i>EvtDmaTransactionConfigureDmaChannel</i> event callback function configures the DMA adapter for a system-mode DMA enabler.


## -prototype


````
EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL EvtDmaTransactionConfigureDmaChannel;

BOOLEAN EvtDmaTransactionConfigureDmaChannel(
  _In_     WDFDMATRANSACTION DmaTransaction,
  _In_     WDFDEVICE         Device,
  _In_     PVOID             Context,
  _In_opt_ PMDL              Mdl,
  _In_     size_t            Offset,
  _In_     size_t            Length
)
{ ... }
````


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object representing the transaction that is being executed.


### -param Device [in]

A handle to the framework device object that the driver specified when it called <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>.


### -param Context [in]

The context pointer that the driver specified in a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsetchannelconfigurationcallback.md">WdfDmaTransactionSetChannelConfigurationCallback</a>.


### -param Mdl [in, optional]

A pointer to a single memory descriptor list (MDL) or MDL chain that describes the buffer associated with the current transfer, or NULL if the last transfer has been completed and the adapter is being freed.


### -param Offset [in]

A byte offset into the buffer specified in the <i>Mdl</i> parameter where the current transfer starts.


### -param Length [in]

The number of bytes being transferred in the current transfer.


## -returns


The <i>EvtDmaTransactionConfigureDmaChannel</i> callback function returns TRUE if it successfully configures the DMA channel. If this callback function returns FALSE, the framework stops the transaction and does not call <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a>.



## -remarks


Drivers register an <i>EvtDmaTransactionConfigureDmaChannel</i> event callback function by calling <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsetchannelconfigurationcallback.md">WdfDmaTransactionSetChannelConfigurationCallback</a>.

The framework calls <i>EvtDmaTransactionConfigureDmaChannel</i> once for each system-profile DMA transfer in the transaction, after allocating the adapter channel but before mapping the transfer and calling <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a>.

The driver can use the <i>EvtDmaTransactionConfigureDmaChannel</i> callback to set any custom programming for the DMA adapter before mapping a transfer.



If the driver experiences an error while configuring the channel, it can stop the DMA transfer by calling <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal.md">WdfDmaTransactionDmaCompletedFinal</a> and, if necessary, completing the request. The driver should then return FALSE from this callback function.



## -see-also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal.md">WdfDmaTransactionDmaCompletedFinal</a>

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsetchannelconfigurationcallback.md">WdfDmaTransactionSetChannelConfigurationCallback</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

