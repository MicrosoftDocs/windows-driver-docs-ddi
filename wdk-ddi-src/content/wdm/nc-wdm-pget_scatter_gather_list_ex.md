---
UID: NC:wdm.PGET_SCATTER_GATHER_LIST_EX
title: PGET_SCATTER_GATHER_LIST_EX
author: windows-driver-content
description: The GetScatterGatherListEx routine allocates the resources that are required for a DMA transfer, builds a scatter/gather list, and calls the driver-supplied AdapterListControl routine to initiate the DMA transfer.
old-location: kernel\getscattergatherlistex.htm
old-project: kernel
ms.assetid: BDEC9AFC-2BA1-4E2C-83B4-F21B220B8B3B
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
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
req.alt-api: GetScatterGatherListEx
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PGET_SCATTER_GATHER_LIST_EX callback



## -description
The <b>GetScatterGatherListEx</b> routine allocates the resources that are required for a DMA transfer, builds a scatter/gather list, and calls the driver-supplied <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine to initiate the DMA transfer.



## -prototype

````
PGET_SCATTER_GATHER_LIST_EX GetScatterGatherListEx;

NTSTATUS GetScatterGatherListEx(
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
  _In_opt_  PDMA_COMPLETION_ROUTINE DmaCompletionRoutine,
  _In_opt_  PVOID                   CompletionContext,
  _Out_opt_ PSCATTER_GATHER_LIST    *ScatterGatherList
)
{ ... }
````


## -parameters

### -param DmaAdapter [in]

A pointer to a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's bus-master DMA device. The caller obtained this pointer from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine.


### -param DeviceObject [in]

A pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure. This structure is the physical device object (PDO) that represents the target device for the requested DMA operation.


### -param DmaTransferContext [in]

A pointer to an initialized DMA transfer context. This context was initialized by a previous call to the <a href="..\wdm\nc-wdm-pinitialize_dma_transfer_context.md">InitializeDmaTransferContext</a> routine. This context must be unique across all adapter allocation requests. To cancel a pending allocation request, the caller must supply the DMA transfer context for the request to the <a href="..\wdm\nc-wdm-pcancel_adapter_channel.md">CancelAdapterChannel</a> routine.


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

### -param DMA_SYNCHRONOUS_CALLBACK

</td>
<td width="60%">
The <b>GetScatterGatherListEx</b> routine is called synchronously. If this flag is set, and the required DMA resources are not immediately available, the call fails and returns STATUS_INSUFFICIENT_RESOURCES.

</td>
</tr>
</table>
 

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set, the <i>ExecutionRoutine</i> parameter is optional and can be NULL. If this flag is not set, <i>ExecutionRoutine</i> must be a valid, non-<b>NULL</b> pointer. For more information about this flag, see the Remarks section.


### -param ExecutionRoutine [in, optional]

A pointer to the driver-supplied <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine that initiates the DMA transfer for the driver. The I/O manager calls the <i>AdapterListControl</i> routine after the required resources are allocated for the adapter object. After the <i>AdapterListControl</i> routine returns, the I/O manager automatically frees the adapter object and the resources that were allocated for this object.

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set, the <i>ExecutionRoutine</i> parameter is optional and can be NULL. If this parameter is NULL, the caller can use the resources allocated by <b>GetScatterGatherListEx</b> to perform the DMA transfer after <b>GetScatterGatherListEx</b> returns. For more information, see the Remarks section.


### -param Context [in, optional]

The driver-determined, adapter-control context. This context is passed to the <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine as the <i>Context</i> parameter.


### -param WriteToDevice [in]

The direction of the DMA transfer. Set this parameter to TRUE for a write operation, which transfers data from memory to the device. Set this parameter to FALSE for a read operation, which transfers data from the device to memory.


### -param DmaCompletionRoutine [in, optional]

Not used. Set to <b>NULL</b>.


### -param CompletionContext [in, optional]

Not used. Set to <b>NULL</b>.


### -param ScatterGatherList [out, optional]

A pointer to a variable into which the routine writes a pointer to the allocated scatter/gather list. This parameter points to a <a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a> structure. The routine allocates this structure and the <b>SCATTER_GATHER_ELEMENT</b> array that it points to.

The <i>ScatterGatherList</i> parameter is optional and can be NULL if the <i>ExecutionRoutine</i> parameter is non-NULL.

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set and the <i>ExecutionRoutine</i> parameter is <b>NULL</b>, <i>ScatterGatherList</i> must be a valid, non-<b>NULL</b> pointer. If <i>ExecutionRoutine</i> is non-<b>NULL</b>, <i>ScatterGatherList</i> is optional and can be <b>NULL</b> if the calling driver does not require the scatter/gather list. The <b>GetScatterGatherListEx</b> call fails if the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set and <i>ScatterGatherList</i> and <i>ExecutionRoutine</i> are both <b>NULL</b>, or if the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is not set and <i>ExecutionRoutine</i> is <b>NULL</b>.


## -returns
<b>GetScatterGatherListEx</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.
<dl>
<dt><b>STATUS_INVALID_PARAMETERS</b></dt>
</dl>The routine failed due to invalid parameter values passed by the caller.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The routine failed to allocate resources required for the DMA transfer.

 


## -remarks
<b>GetScatterGatherListEx</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

Use <b>GetScatterGatherListEx</b> only for bus-master adapters. Do not use this routine for a system DMA adapter.

The driver of a bus-master device can use
     <b>GetScatterGatherListEx</b> to combine the operations performed by the <a href="..\wdm\nc-wdm-pallocate_adapter_channel_ex.md">AllocateAdapterChannelEx</a> and <a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a> routines into a one call. <b>GetScatterGatherListEx</b> performs the following operations:

The allocated resources are automatically released after the <i>AdapterListControl</i> routine returns.  If <b>GetScatterGatherListEx</b> is called synchronously (that is, if the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set), the <i>AdapterListControl</i> routine can be omitted.  In this case, the caller uses the allocated resources to initiate the DMA transfer after <b>GetScatterGatherListEx</b> returns. The caller must explicitly release these resources.

By default, <b>GetScatterGatherListEx</b> returns asynchronously, without waiting for the requested resource allocation to complete. After this return, the caller can, if necessary, cancel the pending allocation request by calling the <a href="..\wdm\nc-wdm-pcancel_adapter_channel.md">CancelAdapterChannel</a> routine.

If the calling driver sets the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag, the <b>GetScatterGatherListEx</b> routine behaves as follows:

If the requested resources are not immediately available, <b>GetScatterGatherListEx</b> does not wait for resources, does not build a scatter/gather list, and does not call the <i>AdapterListControl</i> routine. Instead,  <b>GetScatterGatherListEx</b> fails and returns STATUS_INSUFFICIENT_RESOURCES.

The driver is not required to supply an <i>AdapterListControl</i> routine if the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set.

If the driver supplies an <i>AdapterListControl</i> routine, the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag indicates that this routine is to be called in the context of the calling thread, before <b>GetScatterGatherListEx</b> returns.

If the driver does not supply an <i>AdapterListControl</i> routine, the driver can use the allocated resources and scatter/gather list after <b>GetScatterGatherListEx</b> returns. In this case, the driver must supply a valid, non-NULL <i>ScatterGatherList</i> pointer. In addition, after the driver initiates the DMA transfer, the driver must call the <a href="..\wdm\nc-wdm-pfree_adapter_object.md">FreeAdapterObject</a> routine to free the resources that <b>GetScatterGatherListEx</b> allocated for the adapter object.

<b>GetScatterGatherListEx</b> is an extended version of the <a href="..\wdm\nc-wdm-pget_scatter_gather_list.md">GetScatterGatherList</a> routine. The following features are available only in the extended version:



The calling driver can specify a starting offset for a scatter/gather DMA transfer instead of starting the transfer at the first buffer address at the start of the MDL chain.

The driver can call <a href="..\wdm\nc-wdm-pcancel_adapter_channel.md">CancelAdapterChannel</a> to cancel a pending resource allocation when the adapter object is queued to wait for DMA resources.

The driver can set the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag to request that the driver-supplied <i>AdapterListControl</i> routine be called in the caller's thread, before <b>GetScatterGatherListEx</b> returns.

<b>GetScatterGatherListEx</b> is similar to the <a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a> routine, except that <b>GetScatterGatherListEx</b> automatically allocates the buffer for the scatter/gather list.


## -see-also
<dl>
<dt>
<a href="..\wdm\nc-wdm-driver_control.md">AdapterListControl</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pallocate_adapter_channel_ex.md">AllocateAdapterChannelEx</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pcancel_adapter_channel.md">CancelAdapterChannel</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450991">DmaCompletionRoutine</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546507">FreeAdapterChannel</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pget_scatter_gather_list.md">GetScatterGatherList</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pinitialize_dma_transfer_context.md">InitializeDmaTransferContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PGET_SCATTER_GATHER_LIST_EX callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

