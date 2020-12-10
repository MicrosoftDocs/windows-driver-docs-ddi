---
UID: NC:wdm.PCANCEL_ADAPTER_CHANNEL
title: PCANCEL_ADAPTER_CHANNEL (wdm.h)
description: The CancelAdapterChannel routine tries to cancel a pending request to allocate a DMA channel.
old-location: kernel\canceladapterchannel.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PCANCEL_ADAPTER_CHANNEL callback function"]
ms.keywords: CancelAdapterChannel, CancelAdapterChannel callback function [Kernel-Mode Driver Architecture], PCANCEL_ADAPTER_CHANNEL, PCANCEL_ADAPTER_CHANNEL callback, kernel.canceladapterchannel, wdm/CancelAdapterChannel
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PCANCEL_ADAPTER_CHANNEL
 - wdm/PCANCEL_ADAPTER_CHANNEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - CancelAdapterChannel
---

# PCANCEL_ADAPTER_CHANNEL callback function


## -description

The <b>CancelAdapterChannel</b> routine tries to cancel a pending request to  allocate a DMA channel.

## -parameters

### -param DmaAdapter 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure. This structure is the adapter object that is waiting for the pending resource allocation request to be granted. The caller obtained this pointer from a previous call to the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> routine, and the caller passed this pointer to the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel_ex">AllocateAdapterChannelEx</a>, <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list_ex">GetScatterGatherListEx</a>, or <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pbuild_scatter_gather_list_ex">BuildScatterGatherListEx</a> call that requested the resource allocation.

### -param DeviceObject 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure. This structure is the physical device object (PDO) that represents the target device for the DMA operation for which the DMA channel was requested.

### -param DmaTransferContext 

[in]
A pointer to a DMA transfer context. This parameter value must be the same DMA transfer context that was passed to the <b>AllocateAdapterChannelEx</b>, <b>GetScatterGatherListEx</b>, or <b>BuildScatterGatherListEx</b> call that requested the adapter channel allocation.

## -returns

<b>CancelAdapterChannel</b> returns <b>TRUE</b> if the pending allocation request is successfully canceled. The routine returns <b>FALSE</b> if the request could not be canceled (for example, because the DMA channel was allocated before the request could be canceled).

## -remarks

<b>CancelAdapterChannel</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

<b>CancelAdapterChannel</b> tries to cancel a pending allocation request that was made by an asynchronous call to an allocation routine  such as <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel_ex">AllocateAdapterChannelEx</a>, <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list_ex">GetScatterGatherListEx</a>, or <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pbuild_scatter_gather_list_ex">BuildScatterGatherListEx</a>. When called asynchronously, the allocation routine can return while the allocation request is still pending and before the driver-supplied execution routine (<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_control">AdapterControl</a> or <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_list_control">AdapterListControl</a>) is called. If <b>CancelAdapterChannel</b> successfully cancels the pending allocation request, the resources are not allocated and the execution routine is not called.

If a driver calls <b>AllocateAdapterChannelEx</b> to request resources for a driver-supplied <i>AdapterControl</i> routine, and then calls <b>CancelAdapterChannel</b> to cancel the request, <b>CancelAdapterChannel</b> can return one of the following values:

<ul>
<li>
<b>TRUE</b>, if the adapter object is waiting for the requested allocation when the <b>CancelAdapterChannel</b> call occurs. In this case, <b>CancelAdapterChannel</b> cancels the pending allocation request, and the driver's <i>AdapterControl</i> routine is not called.

</li>
<li>
<b>FALSE</b>, if the <i>AdapterControl</i> routine was already called or is about to be called.

</li>
</ul>
Similarly, if a driver calls <b>GetScatterGatherListEx</b> or <b>BuildScatterGatherListEx</b> to request resources for a driver-supplied <i>AdapterListControl</i> routine, and then calls <b>CancelAdapterChannel</b> to cancel the request, <b>CancelAdapterChannel</b> can return one of the following values:

<ul>
<li>
<b>TRUE</b>, if the adapter object is waiting for the requested allocation when the <b>CancelAdapterChannel</b> call occurs. In this case, <b>CancelAdapterChannel</b> cancels the pending allocation request, and the driver's <i>AdapterListControl</i> routine is not called.

</li>
<li>
<b>FALSE</b>, if the <i>AdapterListControl</i> routine was already called or is about to be called.

</li>
</ul>
<b>CancelAdapterChannel</b> can preemptively cancel future channel allocation requests that use the specified DMA transfer context. For example, if the caller supplies the same DMA transfer context to <b>CancelAdapterChannel</b> and <b>AllocateAdapterChannelEx</b>, and the <b>CancelAdapterChannel</b> call is successful and occurs before the <b>AllocateAdapterChannelEx</b> call, the allocation requested by the <b>AllocateAdapterChannelEx</b> call is automatically canceled.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_control">AdapterControl</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_list_control">AdapterListControl</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel_ex">AllocateAdapterChannelEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pbuild_scatter_gather_list_ex">BuildScatterGatherListEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pcancel_adapter_channel">CancelAdapterChannel</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list_ex">GetScatterGatherListEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>
