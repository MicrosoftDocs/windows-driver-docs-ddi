---
UID: NC:wdm.PFLUSH_ADAPTER_BUFFERS_EX
title: PFLUSH_ADAPTER_BUFFERS_EX (wdm.h)
description: The FlushAdapterBuffersEx routine flushes any data that remains in the data cache at the end of a DMA transfer operation performed by a system DMA controller or bus-master device.
old-location: kernel\flushadapterbuffersex.htm
tech.root: kernel
ms.assetid: D211CB5B-9FE6-4829-950D-F7DDD1A00F76
ms.date: 04/30/2018
keywords: ["PFLUSH_ADAPTER_BUFFERS_EX callback function"]
ms.keywords: FlushAdapterBuffersEx, FlushAdapterBuffersEx callback function [Kernel-Mode Driver Architecture], PFLUSH_ADAPTER_BUFFERS_EX, PFLUSH_ADAPTER_BUFFERS_EX callback, kernel.flushadapterbuffersex, wdm/FlushAdapterBuffersEx
f1_keywords:
 - "wdm/FlushAdapterBuffersEx"
 - "FlushAdapterBuffersEx"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- FlushAdapterBuffersEx
targetos: Windows
req.typenames: 
---

# PFLUSH_ADAPTER_BUFFERS_EX callback function


## -description


The  <b>FlushAdapterBuffersEx</b> routine flushes any data that remains in the data cache at the end of a DMA transfer operation performed by a system DMA controller or bus-master device.


## -parameters




### -param DmaAdapter [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's system DMA channel or bus-master device. The caller obtained this pointer from a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> routine.


### -param Mdl [in]

A pointer to the MDL chain that describes the pages of memory that are to be flushed.  Set this parameter to point to the MDL chain that was used for the DMA transfer. For more information, see the description of the <i>Mdl</i> parameter in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list_ex">GetScatterGatherListEx</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pbuild_scatter_gather_list_ex">BuildScatterGatherListEx</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer_ex">MapTransferEx</a>.


### -param MapRegisterBase [in]

A handle to the map registers that were previously allocated for the adapter object.


### -param Offset [in]

The starting offset relative to the start of the MDL chain to use for the flush operation. Set this parameter to the value that was used as the starting offset for the DMA transfer. For more information, see the description of the <i>Offset</i> parameter in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list_ex">GetScatterGatherListEx</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pbuild_scatter_gather_list_ex">BuildScatterGatherListEx</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer_ex">MapTransferEx</a>.


### -param Length [in]

The number of bytes of data to flush. Set this parameter to the value that was used as the transfer length for the DMA transfer. For more information, see the description of the <i>Length</i> parameter in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list_ex">GetScatterGatherListEx</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pbuild_scatter_gather_list_ex">BuildScatterGatherListEx</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer_ex">MapTransferEx</a>.


### -param WriteToDevice [in]

The direction of the DMA transfer. Set this parameter to the value that was used as the transfer direction for the DMA transfer. For more information, see the description of the <i>WriteToDevice</i> parameter in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list_ex">GetScatterGatherListEx</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pbuild_scatter_gather_list_ex">BuildScatterGatherListEx</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer_ex">MapTransferEx</a>.


## -returns



<b>FlushAdapterBuffersEx</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.

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
</table>
 




## -remarks



<b>FlushAdapterBuffersEx</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

<b>FlushAdapterBuffersEx</b> enables processor cache coherency in hardware platforms that do not implement hardware-enforced cache coherency (bus snooping). In addition, for a system DMA transfer, <b>FlushAdapterBuffersEx</b> flushes any data that remains in the system DMA controller's internal cache.

The driver that initiates a scatter/gather DMA transfer must ensure that all of the transferred data is flushed from the cache after the transfer completes. The driver should call <b>FlushAdapterBuffersEx</b> before the driver completes the IRP that requested the DMA transfer, and before the driver frees the map registers. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/flushing-cached-data-during-dma-operations">Flushing Cached Data during DMA Operations</a>.

<b>FlushAdapterBuffersEx</b> is an extended version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pflush_adapter_buffers">FlushAdapterBuffers</a> routine. <b>FlushAdapterBuffersEx</b> can flush an entire scatter/gather list in one call. In contrast, to use <b>FlushAdapterBuffers</b> to flush a scatter/gather list requires a separate call for each MDL in the MDL chain.

<b>FlushAdapterBuffersEx</b> can be used in place of <b>FlushAdapterBuffers</b> to flush the buffer for a one-packet DMA transfer. In this case, the MDL chain that the <i>Mdl</i> parameter points to contains only one MDL. A benefit of using <b>FlushAdapterBuffersEx</b> in this way is that the caller can specify an offset into the MDL.

If <b>FlushAdapterBuffersEx</b> is called before the DMA transfer operation finishes, this call might cancel the transfer before it can finish or might cause undefined behavior.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pbuild_scatter_gather_list_ex">BuildScatterGatherListEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pflush_adapter_buffers">FlushAdapterBuffers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list_ex">GetScatterGatherListEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer_ex">MapTransferEx</a>
 

 

