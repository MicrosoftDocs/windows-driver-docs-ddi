---
UID: NF:wdfdmatransaction.WdfDmaTransactionInitialize
title: WdfDmaTransactionInitialize function
author: windows-driver-content
description: The WdfDmaTransactionInitialize method initializes a specified DMA transaction.
old-location: wdf\wdfdmatransactioninitialize.htm
old-project: wdf
ms.assetid: cb17b31a-a069-4d41-a613-81a9815ac9a3
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdfdmatransaction/WdfDmaTransactionInitialize, WdfDmaTransactionInitialize, kmdf.wdfdmatransactioninitialize, DFDmaObjectRef_d7f9d480-a08b-4d5e-a4a2-bfc2de6b4d34.xml, WdfDmaTransactionInitialize method, wdf.wdfdmatransactioninitialize
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDmaTransactionInitialize
product: Windows
targetos: Windows
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---

# WdfDmaTransactionInitialize function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionInitialize</b> method initializes a specified DMA transaction.  


## -syntax


````
NTSTATUS WdfDmaTransactionInitialize(
  _In_ WDFDMATRANSACTION   DmaTransaction,
  _In_ PFN_WDF_PROGRAM_DMA EvtProgramDmaFunction,
  _In_ WDF_DMA_DIRECTION   DmaDirection,
  _In_ PMDL                Mdl,
  _In_ PVOID               VirtualAddress,
  _In_ size_t              Length
);
````


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>.


### -param EvtProgramDmaFunction [in]

A pointer to the driver's <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> event callback function. 


### -param DmaDirection [in]

A <a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_direction.md">WDF_DMA_DIRECTION</a>-typed value.


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
The number of scatter/gather elements that was needed to handle the transaction was greater than the value that the driver's call to <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablersetmaximumscattergatherelements.md">WdfDmaEnablerSetMaximumScatterGatherElements</a> specified. 

For transactions that were set for <a href="https://msdn.microsoft.com/windows/hardware/drivers/wdf/">single transfer</a>, one way 
  to fix this is to copy the data to a physically contiguous buffer and then initialize the transaction with that buffer. For example, call <a href="..\wdm\nf-wdm-mmallocatecontiguousmemory.md">MmAllocateContiguousMemory</a>, copy the original buffers into the new one, and then call <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitialize.md">WdfDmaTransactionInitialize</a> again.

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

	Drivers using packet and system DMA can call <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionallocateresources.md">WdfDmaTransactionAllocateResources</a> to reserve a number of map registers from the total allocated to the device. Suppose your driver reserved 4 out of 8 total map registers, but the DMA transfer requires 6. In this case, <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitialize.md">WdfDmaTransactionInitialize</a> fails. To fix, call <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionfreeresources.md">WdfDmaTransactionFreeResources</a> and then call <b>WdfDmaTransactionInitialize</b> again.


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



The <b>WdfDmaTransactionInitialize</b> method prepares a DMA operation for execution, by performing initialization operations such as allocating a transaction's scatter/gather list. After your driver calls <b>WdfDmaTransactionInitialize</b>, the driver must call <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionexecute.md">WdfDmaTransactionExecute</a> to begin executing the transaction.

Framework-based drivers typically call <b>WdfDmaTransactionInitialize</b> from within an <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">I/O queue event callback function</a>. 

If you are creating a DMA transaction that is based on information that a framework request object contains, your driver should call <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest.md">WdfDmaTransactionInitializeUsingRequest</a>.  If you are creating a DMA transaction that is not based on a request object, use either  <b>WdfDmaTransactionInitialize</b> or <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingoffset.md">WdfDmaTransactionInitializeUsingOffset</a>.

The driver can specify an MDL chain in the <i>Mdl</i> parameter of this method. An MDL chain is a sequence of MDL structures that the driver chained together using the <b>Next</b> member of the MDL structure. In framework versions prior to 1.11, only scatter/gather DMA transfers can use MDL chains.  Starting in version 1.11, if the driver is using  DMA version 3, single-packet transfers can also use chained MDLs.

If the buffer that the driver specifies is larger than the maximum transfer length that your driver specified when it called <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a> or <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsetmaximumlength.md">WdfDmaTransactionSetMaximumLength</a>, the framework breaks the transaction into multiple <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">transfers</a>.  

For more information about DMA transactions, see <a href="https://msdn.microsoft.com/1982c3fa-9e4a-4b26-8902-321223d9159f">Creating and Initializing a DMA Transaction</a>. 


#### Examples

The following code example is from the <a href="http://go.microsoft.com/fwlink/p/?linkid=256157">PLX9x5x</a> sample driver. First, the example initializes a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure and creates a DMA transaction object. Next, it obtains an MDL that represents a received I/O request's input buffer, and it obtains the virtual address and length of the buffer. Finally, the example calls <b>WdfDmaTransactionInitialize</b> to initialize the transaction.

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

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>



<a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest.md">WdfDmaTransactionInitializeUsingRequest</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionexecute.md">WdfDmaTransactionExecute</a>



<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablersetmaximumscattergatherelements.md">WdfDmaEnablerSetMaximumScatterGatherElements</a>



<a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_direction.md">WDF_DMA_DIRECTION</a>



<a href="..\wdm\nf-wdm-mmgetmdlbytecount.md">MmGetMdlByteCount</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionInitialize method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

