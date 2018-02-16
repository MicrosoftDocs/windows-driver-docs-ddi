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
req.typenames: "*PWDF_DMA_SYSTEM_PROFILE_CONFIG, WDF_DMA_SYSTEM_PROFILE_CONFIG"
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


#### Examples

To define an <i>EvtDmaTransactionConfigureDmaChannel</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDmaTransactionConfigureDmaChannel</i> callback function that is named <i>MyDmaTransactionConfigureDmaChannel</i>, use the <b>EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL  MyDmaTransactionConfigureDmaChannel;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
BOOLEAN
 MyDmaTransactionConfigureDmaChannel (
    WDFDMATRANSACTION DmaTransaction,
    WDFDEVICE Device,
    PVOID Context,
    PMDL Mdl,
    size_t Offset,
    size_t Length
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL</b> function type is defined in the WdfDmaTransaction.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal.md">WdfDmaTransactionDmaCompletedFinal</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsetchannelconfigurationcallback.md">WdfDmaTransactionSetChannelConfigurationCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DMA_TRANSACTION_CONFIGURE_DMA_CHANNEL callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

