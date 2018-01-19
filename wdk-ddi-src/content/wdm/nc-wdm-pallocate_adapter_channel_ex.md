---
UID: NC:wdm.PALLOCATE_ADAPTER_CHANNEL_EX
title: PALLOCATE_ADAPTER_CHANNEL_EX
author: windows-driver-content
description: The AllocateAdapterChannelEx routine allocates the resources that are needed to perform a DMA transfer, and then calls the driver-supplied AdapterControl routine to initiate the DMA transfer.
old-location: kernel\allocateadapterchannelex.htm
old-project: kernel
ms.assetid: BF255782-0C3E-4F36-BD38-79CE88E7F37D
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
req.alt-api: AllocateAdapterChannelEx
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
req.irql: DISPATCH_LEVEL
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PALLOCATE_ADAPTER_CHANNEL_EX callback



## -description
The <b>AllocateAdapterChannelEx</b> routine allocates the resources that are needed to perform a DMA transfer, and then calls the driver-supplied <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine to initiate the DMA transfer.



## -prototype

````
PALLOCATE_ADAPTER_CHANNEL_EX AllocateAdapterChannelEx;

NTSTATUS AllocateAdapterChannelEx(
  _In_      PDMA_ADAPTER    DmaAdapter,
  _In_      PDEVICE_OBJECT  DeviceObject,
  _In_      PVOID           DmaTransferContext,
  _In_      ULONG           NumberOfMapRegisters,
  _In_      ULONG           Flags,
  _In_opt_  PDRIVER_CONTROL ExecutionRoutine,
  _In_opt_  PVOID           ExecutionContext,
  _Out_opt_ PVOID           *MapRegisterBase
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


### -param NumberOfMapRegisters [in]

The number of map registers to use in the DMA transfer. The calling driver should set this value to the lesser of the number of map registers needed to satisfy the current transfer request, and the number of available map registers. The driver previously called the <a href="..\wdm\nc-wdm-pget_dma_transfer_info.md">GetDmaTransferInfo</a> routine to obtain the number of map registers needed for the transfer, and called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine to obtain the number of available map registers.


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
The <b>AllocateAdapterChannelEx</b> routine is called synchronously. If this flag is set, and the required DMA resources are not immediately available, the call fails and returns STATUS_INSUFFICIENT_RESOURCES.

</td>
</tr>
</table>
 

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set, the <i>ExecutionRoutine</i> parameter is optional and can be NULL. For more information about this flag, see the Remarks section.


### -param ExecutionRoutine [in, optional]

A pointer to the driver-supplied <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine that initiates the DMA transfer for the driver. The I/O manager calls the <i>AdapterControl</i> routine after the required resources are allocated for the adapter object. After the <i>AdapterControl</i> routine returns, the I/O manager automatically frees the adapter object. The I/O manager might additionally free the resources that were allocated for this object, depending on the value returned by this routine.

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set, the <i>ExecutionRoutine</i> is optional and can be <b>NULL</b>.  In this case, the caller can use the resources allocated by <b>AllocateAdapterChannelEx</b>, and later free these resources by calling the <a href="..\wdm\nc-wdm-pfree_adapter_object.md">FreeAdapterObject</a> routine. For more information, see the Remarks section.


### -param ExecutionContext [in, optional]

The driver-determined, adapter-control context. This context is passed to the <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine as the <i>Context</i> parameter.


### -param MapRegisterBase [out, optional]

A pointer to a variable into which the routine writes a handle to the allocated map registers. The caller can supply this handle as a parameter to the <a href="..\wdm\nc-wdm-pflush_adapter_buffers_ex.md">FlushAdapterBuffersEx</a>, <a href="..\wdm\nc-wdm-pflush_adapter_buffers.md">FlushAdapterBuffers</a>, <a href="..\wdm\nc-wdm-pfree_map_registers.md">FreeMapRegisters</a>, or <a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a> routine.

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set, <i>MapRegisterBase</i> must be a valid, non-<b>NULL</b> pointer. If the <i>ExecutionRoutine</i> parameter is non-<b>NULL</b>, <i>MapRegisterBase</i> must be <b>NULL</b>. The call fails if <i>MapRegisterBase</i> is non-<b>NULL</b> and the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is not set, or if <i>MapRegisterBase</i> and <i>ExecutionRoutine</i> are both <b>NULL</b>.


## -returns
<b>AllocateAdapterChannelEx</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.
<dl>
<dt><b>STATUS_INVALID_PARAMETERS</b></dt>
</dl>The routine failed due to invalid parameter values passed by the caller.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The routine failed to allocate resources required for the DMA transfer.

 


## -remarks
<b>AllocateAdapterChannelEx</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

<b>AllocateAdapterChannelEx</b> allocates the resources that are required to perform a DMA operation. These resources include DMA channels and map registers. After all required resources are allocated for use by the DMA adapter, <b>AllocateAdapterChannelEx</b> calls the caller-supplied <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine to initiate the DMA operation.

By default, <b>AllocateAdapterChannelEx</b> returns asynchronously, without waiting for the requested resource allocation to complete. After this return, the caller can, if necessary, cancel the pending allocation request by calling the <a href="..\wdm\nc-wdm-pcancel_adapter_channel.md">CancelAdapterChannel</a> routine.

If the calling driver sets the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag, the <b>AllocateAdapterChannelEx</b> routine behaves as follows:

If the requested DMA resources are not immediately available, <b>AllocateAdapterChannelEx</b> does not wait for resources and does not call the <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine. Instead, <b>AllocateAdapterChannelEx</b> fails and returns STATUS_INSUFFICIENT_RESOURCES.

The driver is not required to supply an <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine if the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set.

If the driver supplies an <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine, the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag indicates that this routine is to be called in the context of the calling thread, before <b>AllocateAdapterChannelEx</b> returns.

If the driver does not supply an <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine, the driver can use the allocated resources after <b>AllocateAdapterChannelEx</b> returns. In this case, the driver must call <a href="..\wdm\nc-wdm-pfree_adapter_object.md">FreeAdapterObject</a> after it finishes using the allocated resources.

<b>AllocateAdapterChannelEx</b> is an extended version of the <a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a> routine.  The following features are available only in the extended version:



The driver can call <a href="..\wdm\nc-wdm-pcancel_adapter_channel.md">CancelAdapterChannel</a> to cancel a pending allocation request when the DMA adapter is queued to wait for DMA resources.

The driver can set the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag to request that the driver-supplied <i>AdapterControl</i> routine be called in the caller's thread, before <b>AllocateAdapterChannelEx</b> returns.


## -see-also
<dl>
<dt>
<a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a>
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
<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pflush_adapter_buffers.md">FlushAdapterBuffers</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pflush_adapter_buffers_ex.md">FlushAdapterBuffersEx</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pfree_adapter_object.md">FreeAdapterObject</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pfree_map_registers.md">FreeMapRegisters</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pget_dma_transfer_info.md">GetDmaTransferInfo</a>
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
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PALLOCATE_ADAPTER_CHANNEL_EX callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

