---
UID: NC:wdfdmatransaction.EVT_WDF_PROGRAM_DMA
title: EVT_WDF_PROGRAM_DMA
author: windows-driver-content
description: A framework-based driver's EvtProgramDma event callback function programs a specified device to perform a DMA transfer operation.
old-location: wdf\evtprogramdma.htm
tech.root: wdf
ms.assetid: c01b94b2-aabf-47dd-952a-06e481579614
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDmaObjectRef_972816f8-bfd1-487d-8ac4-7ef75dcdfa97.xml, EVT_WDF_PROGRAM_DMA, EVT_WDF_PROGRAM_DMA callback, EvtProgramDma, EvtProgramDma callback function, kmdf.evtprogramdma, wdf.evtprogramdma, wdfdmatransaction/EvtProgramDma
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wdfdmatransaction.h
api_name:
-	EvtProgramDma
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_PROGRAM_DMA callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A framework-based driver's <i>EvtProgramDma</i> event callback function programs a specified device to perform a DMA transfer operation.


## -parameters




### -param Transaction [in]

A handle to the DMA transaction object that represents the current DMA transaction.


### -param Device [in]

A handle to a framework device object.


### -param Context [in]

The context pointer that the driver specified in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>.


### -param Direction [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551288">WDF_DMA_DIRECTION</a>-typed value that specifies the direction of the DMA transfer operation.


### -param SgList [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563664">SCATTER_GATHER_LIST</a> structure.


## -returns



The <i>EvtProgramDma</i> callback function must return <b>TRUE</b> if it successfully starts the DMA transfer operation. Otherwise, this callback function must return <b>FALSE</b>. However, the framework currently ignores the return value. 




## -remarks



Drivers register an <i>EvtProgramDma</i> event callback function by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547107">WdfDmaTransactionInitializeUsingRequest</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff547099">WdfDmaTransactionInitialize</a>.

The framework calls a driver's <i>EvtProgramDma</i> event callback function when a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transfer</a> is available. The callback function must program the hardware to start the transfer.

The driver must not manipulate the data buffers associated with the transaction until after <b>WdfDmaTransactionDmaCompleted</b><i>Xxx</i> has returned TRUE.

For single packet transfers, the scatter/gather list that the <i>SgList</i> parameter points to contains a single element.

For more information about this callback function, see <a href="https://msdn.microsoft.com/5e74fe74-d38f-4cca-b0cf-8a6f170c4dc5">Programming DMA Hardware</a>.


#### Examples

To define an <i>EvtProgramDma</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtProgramDma</i> callback function that is named <i>MyProgramDma</i>, use the <b>EVT_WDF_PROGRAM_DMA</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_PROGRAM_DMA  MyProgramDma;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
BOOLEAN
 MyProgramDma (
    WDFDMATRANSACTION  Transaction,
    WDFDEVICE  Device,
    PVOID  Context,
    WDF_DMA_DIRECTION  Direction,
    PSCATTER_GATHER_LIST  SgList
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_PROGRAM_DMA</b> function type is defined in the Wdfdmatransaction.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_PROGRAM_DMA</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547099">WdfDmaTransactionInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547107">WdfDmaTransactionInitializeUsingRequest</a>
 

 

