---
UID: NC:wdm.PALLOCATE_ADAPTER_CHANNEL_EX
title: PALLOCATE_ADAPTER_CHANNEL_EX (wdm.h)
description: The AllocateAdapterChannelEx routine allocates the resources that are needed to perform a DMA transfer, and then calls the driver-supplied AdapterControl routine to initiate the DMA transfer.
old-location: kernel\allocateadapterchannelex.htm
tech.root: kernel
ms.assetid: BF255782-0C3E-4F36-BD38-79CE88E7F37D
ms.date: 04/30/2018
keywords: ["PALLOCATE_ADAPTER_CHANNEL_EX callback function"]
ms.keywords: AllocateAdapterChannelEx, AllocateAdapterChannelEx callback function [Kernel-Mode Driver Architecture], DMA_SYNCHRONOUS_CALLBACK, PALLOCATE_ADAPTER_CHANNEL_EX, PALLOCATE_ADAPTER_CHANNEL_EX callback, kernel.allocateadapterchannelex, wdm/AllocateAdapterChannelEx
f1_keywords:
 - "wdm/AllocateAdapterChannelEx"
 - "AllocateAdapterChannelEx"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- AllocateAdapterChannelEx
targetos: Windows
req.typenames: 
---

# PALLOCATE_ADAPTER_CHANNEL_EX callback function


## -description


The <b>AllocateAdapterChannelEx</b> routine allocates the resources that are needed to perform a DMA transfer, and then calls the driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_control">AdapterControl</a> routine to initiate the DMA transfer.


## -parameters




### -param DmaAdapter 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> routine.


### -param DeviceObject 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure. This structure is the physical device object (PDO) that represents the target device for the requested DMA operation.


### -param DmaTransferContext 
[in]
A pointer to an initialized DMA transfer context. This context was initialized by a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinitialize_dma_transfer_context">InitializeDmaTransferContext</a> routine. This context must be unique across all adapter allocation requests. To cancel a pending allocation request, the caller must supply the DMA transfer context for the request to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pcancel_adapter_channel">CancelAdapterChannel</a> routine.


### -param NumberOfMapRegisters 
[in]
The number of map registers to use in the DMA transfer. The calling driver should set this value to the lesser of the number of map registers needed to satisfy the current transfer request, and the number of available map registers. The driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_dma_transfer_info">GetDmaTransferInfo</a> routine to obtain the number of map registers needed for the transfer, and called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> routine to obtain the number of available map registers.


### -param Flags 
[in]
 The adapter channel allocation flags. The following flag is supported.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="DMA_SYNCHRONOUS_CALLBACK"></a><a id="dma_synchronous_callback"></a><dl>
<dt><b><b>DMA_SYNCHRONOUS_CALLBACK</b></b></dt>
</dl>
</td>
<td width="60%">
The <b>AllocateAdapterChannelEx</b> routine is called synchronously. If this flag is set, and the required DMA resources are not immediately available, the call fails and returns STATUS_INSUFFICIENT_RESOURCES.

</td>
</tr>
</table>
 

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set, the <i>ExecutionRoutine</i> parameter is optional and can be NULL. For more information about this flag, see the Remarks section.


### -param ExecutionRoutine 
[in, optional]
A pointer to the driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_control">AdapterControl</a> routine that initiates the DMA transfer for the driver. The I/O manager calls the <i>AdapterControl</i> routine after the required resources are allocated for the adapter object. After the <i>AdapterControl</i> routine returns, the I/O manager automatically frees the adapter object. The I/O manager might additionally free the resources that were allocated for this object, depending on the value returned by this routine.

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set, the <i>ExecutionRoutine</i> is optional and can be <b>NULL</b>.  In this case, the caller can use the resources allocated by <b>AllocateAdapterChannelEx</b>, and later free these resources by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pfree_adapter_object">FreeAdapterObject</a> routine. For more information, see the Remarks section.


### -param ExecutionContext 
[in, optional]
The driver-determined, adapter-control context. This context is passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_control">AdapterControl</a> routine as the <i>Context</i> parameter.


### -param MapRegisterBase 
[out, optional]
A pointer to a variable into which the routine writes a handle to the allocated map registers. The caller can supply this handle as a parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pflush_adapter_buffers_ex">FlushAdapterBuffersEx</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pflush_adapter_buffers">FlushAdapterBuffers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pfree_map_registers">FreeMapRegisters</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer_ex">MapTransferEx</a> routine.

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set, <i>MapRegisterBase</i> must be a valid, non-<b>NULL</b> pointer. If the <i>ExecutionRoutine</i> parameter is non-<b>NULL</b>, <i>MapRegisterBase</i> must be <b>NULL</b>. The call fails if <i>MapRegisterBase</i> is non-<b>NULL</b> and the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is not set, or if <i>MapRegisterBase</i> and <i>ExecutionRoutine</i> are both <b>NULL</b>.


## -returns



<b>AllocateAdapterChannelEx</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.

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



<b>AllocateAdapterChannelEx</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

<b>AllocateAdapterChannelEx</b> allocates the resources that are required to perform a DMA operation. These resources include DMA channels and map registers. After all required resources are allocated for use by the DMA adapter, <b>AllocateAdapterChannelEx</b> calls the caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_control">AdapterControl</a> routine to initiate the DMA operation.

By default, <b>AllocateAdapterChannelEx</b> returns asynchronously, without waiting for the requested resource allocation to complete. After this return, the caller can, if necessary, cancel the pending allocation request by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pcancel_adapter_channel">CancelAdapterChannel</a> routine.

If the calling driver sets the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag, the <b>AllocateAdapterChannelEx</b> routine behaves as follows:

<ul>
<li>
If the requested DMA resources are not immediately available, <b>AllocateAdapterChannelEx</b> does not wait for resources and does not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_control">AdapterControl</a> routine. Instead, <b>AllocateAdapterChannelEx</b> fails and returns STATUS_INSUFFICIENT_RESOURCES.

</li>
<li>
The driver is not required to supply an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_control">AdapterControl</a> routine if the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set.

</li>
<li>
If the driver supplies an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_control">AdapterControl</a> routine, the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag indicates that this routine is to be called in the context of the calling thread, before <b>AllocateAdapterChannelEx</b> returns.

</li>
<li>
If the driver does not supply an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_control">AdapterControl</a> routine, the driver can use the allocated resources after <b>AllocateAdapterChannelEx</b> returns. In this case, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pfree_adapter_object">FreeAdapterObject</a> after it finishes using the allocated resources.

</li>
</ul>
<b>AllocateAdapterChannelEx</b> is an extended version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel">AllocateAdapterChannel</a> routine.  The following features are available only in the extended version:






## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_control">AdapterControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel">AllocateAdapterChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pcancel_adapter_channel">CancelAdapterChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pflush_adapter_buffers">FlushAdapterBuffers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pflush_adapter_buffers_ex">FlushAdapterBuffersEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pfree_adapter_object">FreeAdapterObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pfree_map_registers">FreeMapRegisters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_dma_transfer_info">GetDmaTransferInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinitialize_dma_transfer_context">InitializeDmaTransferContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer_ex">MapTransferEx</a>
 

 

