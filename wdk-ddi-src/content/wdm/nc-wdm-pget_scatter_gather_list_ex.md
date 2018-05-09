---
UID: NC:wdm.PGET_SCATTER_GATHER_LIST_EX
title: PGET_SCATTER_GATHER_LIST_EX
author: windows-driver-content
description: The GetScatterGatherListEx routine allocates the resources that are required for a DMA transfer, builds a scatter/gather list, and calls the driver-supplied AdapterListControl routine to initiate the DMA transfer.
old-location: kernel\getscattergatherlistex.htm
old-project: kernel
ms.assetid: BDEC9AFC-2BA1-4E2C-83B4-F21B220B8B3B
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: DMA_SYNCHRONOUS_CALLBACK, GetScatterGatherListEx, GetScatterGatherListEx callback function [Kernel-Mode Driver Architecture], PGET_SCATTER_GATHER_LIST_EX, PGET_SCATTER_GATHER_LIST_EX callback, kernel.getscattergatherlistex, wdm/GetScatterGatherListEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	GetScatterGatherListEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# PGET_SCATTER_GATHER_LIST_EX callback function


## -description


The <b>GetScatterGatherListEx</b> routine allocates the resources that are required for a DMA transfer, builds a scatter/gather list, and calls the driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff540513">AdapterListControl</a> routine to initiate the DMA transfer.
<div class="alert"><b>Note</b>  Do not call this routine for a system DMA device.</div><div> </div>

## -parameters




### -param DmaAdapter [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's bus-master DMA device. The caller obtained this pointer from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine.


### -param DeviceObject [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure. This structure is the physical device object (PDO) that represents the target device for the requested DMA operation.


### -param DmaTransferContext [in]

A pointer to an initialized DMA transfer context. This context was initialized by a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451191">InitializeDmaTransferContext</a> routine. This context must be unique across all adapter allocation requests. To cancel a pending allocation request, the caller must supply the DMA transfer context for the request to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406374">CancelAdapterChannel</a> routine.


### -param Mdl [in]

A pointer to an MDL chain that describes the physical page layout for a collection of locked-down buffers in virtual memory. The scatter/gather list for the DMA transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters. For more information about MDL chains, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.


### -param Offset [in]

The starting offset for the scatter/gather DMA transfer. This parameter is a byte offset from the start of the buffer in the first MDL in the MDL chain. If the MDLs in the MDL chain specify a total of N bytes of buffer space, valid values of <i>Offset</i> are in the range 0 to N–1.


### -param Length [in]

The length, in bytes, of the DMA transfer. If the MDL chain specifies a total of N bytes of buffer space, valid values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.


### -param Flags [in]

The adapter channel allocation flags. The following flag is supported.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="DMA_SYNCHRONOUS_CALLBACK"></a><a id="dma_synchronous_callback"></a><dl>
<dt><b>DMA_SYNCHRONOUS_CALLBACK</b></dt>
</dl>
</td>
<td width="60%">
The <b>GetScatterGatherListEx</b> routine is called synchronously. If this flag is set, and the required DMA resources are not immediately available, the call fails and returns STATUS_INSUFFICIENT_RESOURCES.

</td>
</tr>
</table>
 

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set, the <i>ExecutionRoutine</i> parameter is optional and can be NULL. If this flag is not set, <i>ExecutionRoutine</i> must be a valid, non-<b>NULL</b> pointer. For more information about this flag, see the Remarks section.


### -param ExecutionRoutine [in, optional]

A pointer to the driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff540513">AdapterListControl</a> routine that initiates the DMA transfer for the driver. The I/O manager calls the <i>AdapterListControl</i> routine after the required resources are allocated for the adapter object. After the <i>AdapterListControl</i> routine returns, the I/O manager automatically frees the adapter object and the resources that were allocated for this object.

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set, the <i>ExecutionRoutine</i> parameter is optional and can be NULL. If this parameter is NULL, the caller can use the resources allocated by <b>GetScatterGatherListEx</b> to perform the DMA transfer after <b>GetScatterGatherListEx</b> returns. For more information, see the Remarks section.


### -param Context [in, optional]

The driver-determined, adapter-control context. This context is passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540513">AdapterListControl</a> routine as the <i>Context</i> parameter.


### -param WriteToDevice [in]

The direction of the DMA transfer. Set this parameter to TRUE for a write operation, which transfers data from memory to the device. Set this parameter to FALSE for a read operation, which transfers data from the device to memory.


### -param DmaCompletionRoutine [in, optional]

Not used. Set to <b>NULL</b>.


### -param CompletionContext [in, optional]

Not used. Set to <b>NULL</b>.


### -param *ScatterGatherList [out, optional]

A pointer to a variable into which the routine writes a pointer to the allocated scatter/gather list. This parameter points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563664">SCATTER_GATHER_LIST</a> structure. The routine allocates this structure and the <b>SCATTER_GATHER_ELEMENT</b> array that it points to.

The <i>ScatterGatherList</i> parameter is optional and can be NULL if the <i>ExecutionRoutine</i> parameter is non-NULL.

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set and the <i>ExecutionRoutine</i> parameter is <b>NULL</b>, <i>ScatterGatherList</i> must be a valid, non-<b>NULL</b> pointer. If <i>ExecutionRoutine</i> is non-<b>NULL</b>, <i>ScatterGatherList</i> is optional and can be <b>NULL</b> if the calling driver does not require the scatter/gather list. The <b>GetScatterGatherListEx</b> call fails if the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set and <i>ScatterGatherList</i> and <i>ExecutionRoutine</i> are both <b>NULL</b>, or if the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is not set and <i>ExecutionRoutine</i> is <b>NULL</b>.


## -returns



<b>GetScatterGatherListEx</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETERS</b></dt>
</dl>
</td>
<td width="60%">
The routine failed due to invalid parameter values passed by the caller.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The routine failed to allocate resources required for the DMA transfer.

</td>
</tr>
</table>
 




## -remarks



<b>GetScatterGatherListEx</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

Use <b>GetScatterGatherListEx</b> only for bus-master adapters. Do not use this routine for a system DMA adapter.

The driver of a bus-master device can use
     <b>GetScatterGatherListEx</b> to combine the operations performed by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406340">AllocateAdapterChannelEx</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh406521">MapTransferEx</a> routines into a one call. <b>GetScatterGatherListEx</b> performs the following operations:

<ol>
<li>Allocates the resources that are required for the DMA transfer.</li>
<li>Builds a scatter/gather list based on the values of the <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters.</li>
<li>Calls the driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff540513">AdapterListControl</a> routine and supplies the scatter/gather list to this routine as a parameter.</li>
</ol>
The allocated resources are automatically released after the <i>AdapterListControl</i> routine returns.  If <b>GetScatterGatherListEx</b> is called synchronously (that is, if the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set), the <i>AdapterListControl</i> routine can be omitted.  In this case, the caller uses the allocated resources to initiate the DMA transfer after <b>GetScatterGatherListEx</b> returns. The caller must explicitly release these resources.

By default, <b>GetScatterGatherListEx</b> returns asynchronously, without waiting for the requested resource allocation to complete. After this return, the caller can, if necessary, cancel the pending allocation request by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406374">CancelAdapterChannel</a> routine.

If the calling driver sets the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag, the <b>GetScatterGatherListEx</b> routine behaves as follows:

<ul>
<li>
If the requested resources are not immediately available, <b>GetScatterGatherListEx</b> does not wait for resources, does not build a scatter/gather list, and does not call the <i>AdapterListControl</i> routine. Instead,  <b>GetScatterGatherListEx</b> fails and returns STATUS_INSUFFICIENT_RESOURCES.

</li>
<li>
The driver is not required to supply an <i>AdapterListControl</i> routine if the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set.

</li>
<li>
If the driver supplies an <i>AdapterListControl</i> routine, the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag indicates that this routine is to be called in the context of the calling thread, before <b>GetScatterGatherListEx</b> returns.

</li>
<li>
If the driver does not supply an <i>AdapterListControl</i> routine, the driver can use the allocated resources and scatter/gather list after <b>GetScatterGatherListEx</b> returns. In this case, the driver must supply a valid, non-NULL <i>ScatterGatherList</i> pointer. In addition, after the driver initiates the DMA transfer, the driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451107">FreeAdapterObject</a> routine to free the resources that <b>GetScatterGatherListEx</b> allocated for the adapter object.

</li>
</ul>
<b>GetScatterGatherListEx</b> is an extended version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546531">GetScatterGatherList</a> routine. The following features are available only in the extended version:



<b>GetScatterGatherListEx</b> is similar to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406371">BuildScatterGatherListEx</a> routine, except that <b>GetScatterGatherListEx</b> automatically allocates the buffer for the scatter/gather list.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540513">AdapterListControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406340">AllocateAdapterChannelEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406371">BuildScatterGatherListEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406374">CancelAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450991">DmaCompletionRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546507">FreeAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546531">GetScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451191">InitializeDmaTransferContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406521">MapTransferEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563664">SCATTER_GATHER_LIST</a>
 

 

