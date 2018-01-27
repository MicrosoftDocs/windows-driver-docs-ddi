---
UID: NC:wdm.PBUILD_SCATTER_GATHER_LIST_EX
title: PBUILD_SCATTER_GATHER_LIST_EX
author: windows-driver-content
description: The BuildScatterGatherListEx routine allocates the resources that are required for a DMA transfer, builds a scatter/gather list, and calls the driver-supplied AdapterListControl routine to initiate the DMA transfer.
old-location: kernel\buildscattergatherlistex.htm
old-project: kernel
ms.assetid: A1A89D52-5F39-45E4-AFBE-20DAD0E49442
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.buildscattergatherlistex, BuildScatterGatherListEx, BuildScatterGatherListEx callback function [Kernel-Mode Driver Architecture], BuildScatterGatherListEx, PBUILD_SCATTER_GATHER_LIST_EX, PBUILD_SCATTER_GATHER_LIST_EX, wdm/BuildScatterGatherListEx, DMA_SYNCHRONOUS_CALLBACK
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
req.irql: DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Wdm.h
apiname: 
-	BuildScatterGatherListEx
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PBUILD_SCATTER_GATHER_LIST_EX callback


## -description


The <b>BuildScatterGatherListEx</b> routine allocates the resources that are required for a DMA transfer, builds a scatter/gather list, and calls  the driver-supplied <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine to initiate the DMA transfer.
<div class="alert"><b>Note</b>  Do not call this routine for a system DMA device.</div><div> </div>

## -prototype


````
PBUILD_SCATTER_GATHER_LIST_EX BuildScatterGatherListEx;

NTSTATUS BuildScatterGatherListEx(
  _In_      PDMA_ADAPTER            DmaAdapter,
  _In_      PDEVICE_OBJECT          DeviceObject,
  _In_      PVOID                   DmaTransferContext,
  _In_      PMDL                    Mdl,
  _In_      ULONGLONG               Offset,
  _In_      ULONG                   Length,
  _In_      ULONG                   Flags,
  _In_opt_  PDRIVER_LIST_CONTROL    ExecutionRoutine,
  _In_opt_  PVOID                   Context,
  _In_      BOOLEAN                 WriteToDevice,
  _In_      PVOID                   ScatterGatherBuffer,
  _In_      ULONG                   ScatterGatherBufferLength,
  _In_opt_  PDMA_COMPLETION_ROUTINE DmaCompletionRoutine,
  _In_opt_  PVOID                   CompletionContext,
  _Out_opt_ PSCATTER_GATHER_LIST    *ScatterGatherList
)
{ ... }
````


## -parameters




### -param DmaAdapter [in]

A pointer to a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine.


### -param DeviceObject [in]

A pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure. This structure is the physical device object (PDO) that represents the target device for the requested DMA operation.


### -param DmaTransferContext [in]

A pointer to an initialized DMA transfer context. This context was initialized by a previous call to the <a href="..\wdm\nc-wdm-pinitialize_dma_transfer_context.md">InitializeDmaTransferContext</a> routine. This context must be unique across all adapter allocation requests. To cancel a pending allocation request, the caller must supply the DMA transfer context for the request to the <a href="..\wdm\nc-wdm-pcancel_adapter_channel.md">CancelAdapterChannel</a> routine.


### -param Mdl [in]

A pointer to an MDL chain that describes the physical page layout for a collection of locked-down buffers in virtual memory. The scatter/gather list for the DMA transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters. For more information about MDL chains, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.


### -param Offset [in]

The starting offset for the scatter/gather DMA transfer. This parameter is a byte offset from the start of the buffer in the first MDL in the MDL chain. If the MDLs in the MDL chain specify a total of N bytes of buffer space, valid values of <i>Offset</i> are in the range 0 to N–1.


### -param Length [in]

The size, in bytes, of the DMA transfer. If the MDL chain specifies a total of N bytes of buffer space, valid values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.


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
The <b>BuildScatterGatherListEx</b> routine is called synchronously. If this flag is set, and the required DMA resources are not immediately available, the call fails and returns STATUS_INSUFFICIENT_RESOURCES.

</td>
</tr>
</table> 

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set, the <i>ExecutionRoutine</i> parameter is optional and can be <b>NULL</b>. If this flag is not set, <i>ExecutionRoutine</i> must be a valid, non-<b>NULL</b> pointer. For more information about this flag, see the Remarks section.


### -param ExecutionRoutine [in, optional]

A pointer to the driver-supplied <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine that initiates the DMA transfer for the driver. The I/O manager calls the <i>AdapterListControl</i> routine after the required resources are allocated for the adapter object. After the <i>AdapterListControl</i> routine returns, the I/O manager automatically frees the adapter object and the resources that were allocated for this object.

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set, <i>ExecutionRoutine</i> is optional and can be <b>NULL</b>.  If <i>ExecutionRoutine</i> is <b>NULL</b>, the caller can use the resources allocated by <b>BuildScatterGatherListEx</b>. For more information, see the Remarks section.


### -param Context [in, optional]

The driver-determined, adapter-control context. This context is passed to the <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine as the <i>Context</i> parameter.


### -param WriteToDevice [in]

The direction of the DMA transfer. Set this parameter to <b>TRUE</b> for a write operation, which transfers data from memory to the device. Set this parameter to <b>FALSE</b> for a read operation, which transfers data from the device to memory.


### -param ScatterGatherBuffer [in]

A pointer to a caller-allocated buffer into which the routine writes the scatter/gather list for the DMA transfer. This list begins with a <a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a> structure, which is followed by a <b>SCATTER_GATHER_ELEMENT</b> array.


### -param ScatterGatherLength



### -param DmaCompletionRoutine [in, optional]

Not used. Set to <b>NULL</b>.


### -param CompletionContext [in, optional]

Not used. Set to <b>NULL</b>.


### -param ScatterGatherList [out, optional]

A pointer to a variable into which the routine writes a pointer to the scatter/gather list for the DMA transfer. This list begins with a <a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a> structure, which contains a pointer to a <b>SCATTER_GATHER_ELEMENT</b> array. This output pointer always matches the <i>ScatterGatherBuffer</i> parameter value.

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set and the <i>ExecutionRoutine</i> parameter is <b>NULL</b>, <i>ScatterGatherList</i> must be a valid, non-<b>NULL</b> pointer. If <i>ExecutionRoutine</i> is non-<b>NULL</b>, <i>ScatterGatherList</i> is optional and can be <b>NULL</b> if the calling driver does not require the scatter/gather list. The <b>BuildScatterGatherListEx</b> call fails if the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set and <i>ScatterGatherList</i> and <i>ExecutionRoutine</i> are both <b>NULL</b>, or if the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is not set and <i>ExecutionRoutine</i> is <b>NULL</b>.


#### - ScatterGatherBufferLength [in]

The size, in bytes, of the buffer passed in the <i>ScatterGatherBuffer</i> parameter. The allocated buffer size must be large enough to contain the scatter/gather list, plus internal data that the operating system stores in this buffer. To calculate the required buffer size, call the <a href="..\wdm\nc-wdm-pget_dma_transfer_info.md">GetDmaTransferInfo</a> or <a href="..\wdm\nc-wdm-pcalculate_scatter_gather_list_size.md">CalculateScatterGatherList</a> routine.


## -returns


<b>BuildScatterGatherListEx</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.
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
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The caller-supplied buffer in <i>ScatterGatherBuffer</i> is too small to contain the scatter/gather list.

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


<b>BuildScatterGatherListEx</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

Use <b>BuildScatterGatherListEx</b> only for bus-master adapters. Do not use this routine for a system DMA adapter.

<b>BuildScatterGatherListEx</b> is similar to the <a href="..\wdm\nc-wdm-pget_scatter_gather_list_ex.md">GetScatterGatherListEx</a> routine, except that it requires the caller to allocate the buffer for the scatter/gather list.

For example, a driver might preallocate one or more scatter/gather buffers during device initialization. Later, a <b>BuildScatterGatherListEx</b> call that uses such a buffer can succeed in conditions of low memory availability that might cause a <b>GetScatterGatherListEx</b> call to fail.

By default, <b>BuildScatterGatherListEx</b> returns asynchronously, without waiting for the requested resource allocation to complete. After this return, the caller can, if necessary, cancel the pending allocation request by calling the <a href="..\wdm\nc-wdm-pcancel_adapter_channel.md">CancelAdapterChannel</a> routine.

If the calling driver sets the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag, the <b>BuildScatterGatherListEx</b> routine behaves as follows:
<ul>
<li>
If the requested resources are not immediately available, <b>BuildScatterGatherListEx</b> does not wait for resources, does not build a scatter/gather list, and does not call the <i>AdapterListControl</i> routine. Instead,  <b>BuildScatterGatherListEx</b> fails and returns STATUS_INSUFFICIENT_RESOURCES.

</li>
<li>
The driver is not required to supply an <i>AdapterListControl</i> routine if the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set.

</li>
<li>
If the driver supplies an <i>AdapterListControl</i> routine, the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag indicates that this routine is to be called in the context of the calling thread, before <b>BuildScatterGatherListEx</b> returns.

</li>
<li>
If the driver does not supply an <i>AdapterListControl</i> routine, the driver can use the allocated resources and scatter/gather list after <b>BuildScatterGatherListEx</b> returns. In this case, the driver must supply a valid, non-<b>NULL</b> <i>ScatterGatherList</i> pointer. In addition, after the driver-initiated DMA transfer completes, the driver must call the <a href="..\wdm\nc-wdm-pfree_adapter_object.md">FreeAdapterObject</a> routine to free the resources that <b>BuildScatterGatherListEx</b> allocated for the adapter object.

</li>
</ul><b>BuildScatterGatherListEx</b> is an extended version of the <a href="..\wdm\nc-wdm-pbuild_scatter_gather_list.md">BuildScatterGatherList</a> routine. The following list summarizes the features that are available only in the extended version:





## -see-also

<a href="..\wdm\nc-wdm-pget_scatter_gather_list.md">GetScatterGatherList</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450991">DmaCompletionRoutine</a>

<a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a>

<a href="..\wdm\nc-wdm-pcalculate_scatter_gather_list_size.md">CalculateScatterGatherList</a>

<a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a>

<a href="..\wdm\nc-wdm-pallocate_adapter_channel_ex.md">AllocateAdapterChannelEx</a>

<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>

<a href="..\wdm\nc-wdm-pget_scatter_gather_list_ex.md">GetScatterGatherListEx</a>

<a href="..\wdm\nc-wdm-pfree_adapter_object.md">FreeAdapterObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PBUILD_SCATTER_GATHER_LIST_EX callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

