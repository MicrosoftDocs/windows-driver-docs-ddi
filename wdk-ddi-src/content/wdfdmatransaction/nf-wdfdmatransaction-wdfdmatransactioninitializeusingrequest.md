---
UID: NF:wdfdmatransaction.WdfDmaTransactionInitializeUsingRequest
title: WdfDmaTransactionInitializeUsingRequest function
author: windows-driver-content
description: The WdfDmaTransactionInitializeUsingRequest method initializes a specified DMA transaction by using the parameters of a specified I/O request.
old-location: wdf\wdfdmatransactioninitializeusingrequest.htm
old-project: wdf
ms.assetid: 5a59c1cc-b5a9-4e94-966d-9998a98d6ad2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDmaObjectRef_b61c1d2b-b62e-4f04-b7ff-53a8e819062a.xml, WdfDmaTransactionInitializeUsingRequest, WdfDmaTransactionInitializeUsingRequest method, kmdf.wdfdmatransactioninitializeusingrequest, wdf.wdfdmatransactioninitializeusingrequest, wdfdmatransaction/WdfDmaTransactionInitializeUsingRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DeferredRequestCompleted, DriverCreate, KmdfIrql, KmdfIrql2, RequestCompleted, RequestCompletedLocal
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
-	WdfDmaTransactionInitializeUsingRequest
product: Windows
targetos: Windows
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---

# WdfDmaTransactionInitializeUsingRequest function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionInitializeUsingRequest</b> method initializes a specified DMA transaction by using the parameters of a specified I/O request. 


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>.


### -param Request [in]

A handle to a framework request object.


### -param EvtProgramDmaFunction [in]

A pointer to the driver's <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> event callback function. 


### -param DmaDirection [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551288">WDF_DMA_DIRECTION</a>-typed value that specifies the direction of the DMA transfer.


## -returns



<b>WdfDmaTransactionInitializeUsingRequest</b> returns STATUS_SUCCESS if the operation succeeds.  Otherwise, the method might return one of the values described in the Return values section of <a href="https://msdn.microsoft.com/library/windows/hardware/ff547099">WdfDmaTransactionInitialize</a>.

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfDmaTransactionInitializeUsingRequest</b> method prepares a DMA operation for execution, by performing initialization operations such as setting up a transaction's scatter/gather list. After your driver calls <b>WdfDmaTransactionInitializeUsingRequest</b>, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>.

The driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549969">WdfRequestGetParameters</a> to obtain a request's type. The value that the driver specifies for the <i>DmaDirection</i> parameter must be appropriate for the request type, as follows:

<ul>
<li> The <i>DmaDirection</i> value must be <b>WdfDmaDirectionReadFromDevice</b> if: <ul>
<li> The request type is <b>WdfRequestTypeRead</b></li>
<li>The request type is <b>WdfRequestTypeDeviceControl</b> or <b>WdfRequestTypeDeviceControlInternal</b> and the I/O control code specifies a transfer type of METHOD_OUT_DIRECT  </li>
</ul>
</li>
<li>
 The <i>DmaDirection</i> value must be <b>WdfDmaDirectionWriteToDevice</b> if: 

<ul>
<li>
 The request type is <b>WdfRequestTypeWrite</b>

</li>
<li>
The request type is <b>WdfRequestTypeDeviceControl</b> or <b>WdfRequestTypeDeviceControlInternal</b> and the I/O control code specifies a transfer type of METHOD_IN_DIRECT  

</li>
</ul>
</li>
</ul>
For more information about transfer types for I/O control codes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543023">Defining I/O Control Codes</a>.

Framework-based drivers typically call <b>WdfDmaTransactionInitializeUsingRequest</b> from within an <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">I/O queue event callback function</a>. 

Your driver should call <b>WdfDmaTransactionInitializeUsingRequest</b> if you are creating a DMA transaction that is based on information that a framework request object contains. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff547099">WdfDmaTransactionInitialize</a> if you are creating a DMA transaction that is not based on a request object.

If the buffer that the request object describes is larger than the maximum transfer length that your driver specified when it called <a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff547127">WdfDmaTransactionSetMaximumLength</a>, the framework breaks the transaction into multiple <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">transfers</a>.  

For more information about DMA transactions, see <a href="https://msdn.microsoft.com/1982c3fa-9e4a-4b26-8902-321223d9159f">Creating and Initializing a DMA Transaction</a>. 


#### Examples

For a code example that uses <b>WdfDmaTransactionInitializeUsingRequest</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551288">WDF_DMA_DIRECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547014">WdfDmaEnablerSetMaximumScatterGatherElements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547099">WdfDmaTransactionInitialize</a>
 

 

