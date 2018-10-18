---
UID: NF:wdfdmatransaction.WdfDmaTransactionInitialize
title: WdfDmaTransactionInitialize function
author: windows-driver-content
description: The WdfDmaTransactionInitialize method initializes a specified DMA transaction.
old-location: wdf\wdfdmatransactioninitialize.htm
tech.root: wdf
ms.assetid: cb17b31a-a069-4d41-a613-81a9815ac9a3
ms.date: 2/26/2018
ms.keywords: DFDmaObjectRef_d7f9d480-a08b-4d5e-a4a2-bfc2de6b4d34.xml, WdfDmaTransactionInitialize, WdfDmaTransactionInitialize method, kmdf.wdfdmatransactioninitialize, wdf.wdfdmatransactioninitialize, wdfdmatransaction/WdfDmaTransactionInitialize
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DeferredRequestCompleted, DriverCreate, KmdfIrql, KmdfIrql2, MdlAfterReqCompletedIntIoctlA, MdlAfterReqCompletedIoctlA, MdlAfterReqCompletedReadA, MdlAfterReqCompletedWriteA, RequestCompleted, RequestCompletedLocal
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
-	WdfDmaTransactionInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionInitialize function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaTransactionInitialize</b> method initializes a specified DMA transaction.  


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>.


### -param EvtProgramDmaFunction [in]

A pointer to the driver's <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> event callback function. 


### -param DmaDirection [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551288">WDF_DMA_DIRECTION</a>-typed value.


### -param Mdl [in]

A pointer to a memory descriptor list (MDL) that describes the buffer that will be used for the DMA transaction. See more information in <b>Remarks</b>.


### -param VirtualAddress [in]

The virtual address of the buffer that will be used for the DMA transaction.


### -param Length [in]

The number of bytes to be transferred.


## -returns



<b>WdfDmaTransactionInitialize</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A scatter/gather list could not be allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_TOO_FRAGMENTED</b></dt>
</dl>
</td>
<td width="60%">
The number of scatter/gather elements that was needed to handle the transaction was greater than the value that the driver's call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547014">WdfDmaEnablerSetMaximumScatterGatherElements</a> specified. 

For transactions that were set for <a href="https://msdn.microsoft.com/windows/hardware/drivers/wdf/">single transfer</a>, one way 
  to fix this is to copy the data to a physically contiguous buffer and then initialize the transaction with that buffer. For example, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff554460">MmAllocateContiguousMemory</a>, copy the original buffers into the new one, and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547099">WdfDmaTransactionInitialize</a> again.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_NOT_ENOUGH_MAP_REGISTERS</b></dt>
</dl>
</td>
<td width="60%">
This return value applies only to transactions that were set for <a href="https://msdn.microsoft.com/windows/hardware/drivers/wdf/">single transfer</a>.  

The number of map registers needed to map the transaction is larger than the number the DMA adapter has reserved.

To fix, 	the driver might reduce the number of required map registers by combining an MDL chain into a single MDL.

	Drivers using packet and system DMA can call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451123">WdfDmaTransactionAllocateResources</a> to reserve a number of map registers from the total allocated to the device. Suppose your driver reserved 4 out of 8 total map registers, but the DMA transfer requires 6. In this case, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547099">WdfDmaTransactionInitialize</a> fails. To fix, call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451177">WdfDmaTransactionFreeResources</a> and then call <b>WdfDmaTransactionInitialize</b> again.


 Drivers using scatter/gather DMA cannot reserve map registers.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_TOO_MANY_TRANSFERS</b></dt>
</dl>
</td>
<td width="60%">
This return value applies only to transactions that were set for <a href="https://msdn.microsoft.com/windows/hardware/drivers/wdf/">single transfer</a>.  

The transaction’s total length exceeds the device’s maximum transfer size.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfDmaTransactionInitialize</b> method prepares a DMA operation for execution, by performing initialization operations such as allocating a transaction's scatter/gather list. After your driver calls <b>WdfDmaTransactionInitialize</b>, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a> to begin executing the transaction.

Framework-based drivers typically call <b>WdfDmaTransactionInitialize</b> from within an <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">I/O queue event callback function</a>. 

If you are creating a DMA transaction that is based on information that a framework request object contains, your driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547107">WdfDmaTransactionInitializeUsingRequest</a>.  If you are creating a DMA transaction that is not based on a request object, use either  <b>WdfDmaTransactionInitialize</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/hh451182">WdfDmaTransactionInitializeUsingOffset</a>.

The driver can specify an MDL chain in the <i>Mdl</i> parameter of this method. An MDL chain is a sequence of MDL structures that the driver chained together using the <b>Next</b> member of the MDL structure. In framework versions prior to 1.11, only scatter/gather DMA transfers can use MDL chains.  Starting in version 1.11, if the driver is using  DMA version 3, single-packet transfers can also use chained MDLs.

If the buffer that the driver specifies is larger than the maximum transfer length that your driver specified when it called <a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff547127">WdfDmaTransactionSetMaximumLength</a>, the framework breaks the transaction into multiple <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">transfers</a>.  

For more information about DMA transactions, see <a href="https://msdn.microsoft.com/1982c3fa-9e4a-4b26-8902-321223d9159f">Creating and Initializing a DMA Transaction</a>. 


#### Examples

The following code example is from the <a href="http://go.microsoft.com/fwlink/p/?linkid=256157">PLX9x5x</a> sample driver. First, the example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure and creates a DMA transaction object. Next, it obtains an MDL that represents a received I/O request's input buffer, and it obtains the virtual address and length of the buffer. Finally, the example calls <b>WdfDmaTransactionInitialize</b> to initialize the transaction.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_OBJECT_ATTRIBUTES  attributes;
PMDL  mdl;
PVOID  virtualAddress;
ULONG  length;
NTSTATUS  status;

WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(
                                        &amp;attributes,
                                        TRANSACTION_CONTEXT
                                        );

status = WdfDmaTransactionCreate(
                                 devExt-&gt;DmaEnabler,
                                 &amp;attributes,
                                 &amp;dmaTransaction
                                 );
if(!NT_SUCCESS(status)) {
    goto CleanUp;
}

status = WdfRequestRetrieveInputWdmMdl(
                                       Request,
                                       &amp;mdl
                                       );
if (!NT_SUCCESS(status)) {
    goto CleanUp;
}

virtualAddress = MmGetMdlVirtualAddress(mdl);
length = MmGetMdlByteCount(mdl);

status = WdfDmaTransactionInitialize(
                                     dmaTransaction,
                                     PLxEvtProgramWriteDma,
                                     WdfDmaDirectionWriteToDevice,
                                     mdl,
                                     virtualAddress,
                                     length
                                     );
if(!NT_SUCCESS(status)) {
    goto CleanUp;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554530">MmGetMdlByteCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551288">WDF_DMA_DIRECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547014">WdfDmaEnablerSetMaximumScatterGatherElements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547107">WdfDmaTransactionInitializeUsingRequest</a>
 

 

