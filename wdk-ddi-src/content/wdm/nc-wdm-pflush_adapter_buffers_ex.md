---
UID: NC:wdm.PFLUSH_ADAPTER_BUFFERS_EX
title: PFLUSH_ADAPTER_BUFFERS_EX
author: windows-driver-content
description: The FlushAdapterBuffersEx routine flushes any data that remains in the data cache at the end of a DMA transfer operation performed by a system DMA controller or bus-master device.
old-location: kernel\flushadapterbuffersex.htm
old-project: kernel
ms.assetid: D211CB5B-9FE6-4829-950D-F7DDD1A00F76
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: FlushAdapterBuffersEx, FlushAdapterBuffersEx callback function [Kernel-Mode Driver Architecture], PFLUSH_ADAPTER_BUFFERS_EX, kernel.flushadapterbuffersex, wdm/FlushAdapterBuffersEx
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
-	FlushAdapterBuffersEx
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PFLUSH_ADAPTER_BUFFERS_EX callback


## -description


The  <b>FlushAdapterBuffersEx</b> routine flushes any data that remains in the data cache at the end of a DMA transfer operation performed by a system DMA controller or bus-master device.


## -prototype


````
PFLUSH_ADAPTER_BUFFERS_EX FlushAdapterBuffersEx;

NTSTATUS FlushAdapterBuffersEx(
  _In_ PDMA_ADAPTER DmaAdapter,
  _In_ PMDL         Mdl,
  _In_ PVOID        MapRegisterBase,
  _In_ ULONGLONG    Offset,
  _In_ ULONG        Length,
  _In_ BOOLEAN      WriteToDevice
)
{ ... }
````


## -parameters




### -param DmaAdapter [in]

A pointer to a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's system DMA channel or bus-master device. The caller obtained this pointer from a previous call to the <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> routine.


### -param Mdl [in]

A pointer to the MDL chain that describes the pages of memory that are to be flushed.  Set this parameter to point to the MDL chain that was used for the DMA transfer. For more information, see the description of the <i>Mdl</i> parameter in <a href="..\wdm\nc-wdm-pget_scatter_gather_list_ex.md">GetScatterGatherListEx</a>, <a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a>, or <a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a>.


### -param MapRegisterBase [in]

A handle to the map registers that were previously allocated for the adapter object.


### -param Offset [in]

The starting offset relative to the start of the MDL chain to use for the flush operation. Set this parameter to the value that was used as the starting offset for the DMA transfer. For more information, see the description of the <i>Offset</i> parameter in <a href="..\wdm\nc-wdm-pget_scatter_gather_list_ex.md">GetScatterGatherListEx</a>, <a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a>, or <a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a>.


### -param Length [in]

The number of bytes of data to flush. Set this parameter to the value that was used as the transfer length for the DMA transfer. For more information, see the description of the <i>Length</i> parameter in <a href="..\wdm\nc-wdm-pget_scatter_gather_list_ex.md">GetScatterGatherListEx</a>, <a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a>, or <a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a>.


### -param WriteToDevice [in]

The direction of the DMA transfer. Set this parameter to the value that was used as the transfer direction for the DMA transfer. For more information, see the description of the <i>WriteToDevice</i> parameter in <a href="..\wdm\nc-wdm-pget_scatter_gather_list_ex.md">GetScatterGatherListEx</a>, <a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a>, or <a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a>.


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



<b>FlushAdapterBuffersEx</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

<b>FlushAdapterBuffersEx</b> enables processor cache coherency in hardware platforms that do not implement hardware-enforced cache coherency (bus snooping). In addition, for a system DMA transfer, <b>FlushAdapterBuffersEx</b> flushes any data that remains in the system DMA controller's internal cache.

The driver that initiates a scatter/gather DMA transfer must ensure that all of the transferred data is flushed from the cache after the transfer completes. The driver should call <b>FlushAdapterBuffersEx</b> before the driver completes the IRP that requested the DMA transfer, and before the driver frees the map registers. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545924">Flushing Cached Data during DMA Operations</a>.

<b>FlushAdapterBuffersEx</b> is an extended version of the <a href="..\wdm\nc-wdm-pflush_adapter_buffers.md">FlushAdapterBuffers</a> routine. <b>FlushAdapterBuffersEx</b> can flush an entire scatter/gather list in one call. In contrast, to use <b>FlushAdapterBuffers</b> to flush a scatter/gather list requires a separate call for each MDL in the MDL chain.

<b>FlushAdapterBuffersEx</b> can be used in place of <b>FlushAdapterBuffers</b> to flush the buffer for a one-packet DMA transfer. In this case, the MDL chain that the <i>Mdl</i> parameter points to contains only one MDL. A benefit of using <b>FlushAdapterBuffersEx</b> in this way is that the caller can specify an offset into the MDL.

If <b>FlushAdapterBuffersEx</b> is called before the DMA transfer operation finishes, this call might cancel the transfer before it can finish or might cause undefined behavior.




## -see-also

<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>



<a href="..\wdm\nc-wdm-pflush_adapter_buffers.md">FlushAdapterBuffers</a>



<a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a>



<a href="..\wdm\ns-wdm-_dma_adapter_info.md">DMA_ADAPTER</a>



<a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a>



<a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>



<a href="..\wdm\nc-wdm-pget_scatter_gather_list_ex.md">GetScatterGatherListEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PFLUSH_ADAPTER_BUFFERS_EX callback function%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

