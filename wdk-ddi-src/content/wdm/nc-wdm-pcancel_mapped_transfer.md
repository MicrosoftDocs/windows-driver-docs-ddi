---
UID: NC:wdm.PCANCEL_MAPPED_TRANSFER
title: PCANCEL_MAPPED_TRANSFER (wdm.h)
description: The CancelMappedTransfer routine cancels a system DMA transfer that is currently mapped to an adapter.
old-location: kernel\cancelmappedtransfer.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PCANCEL_MAPPED_TRANSFER callback function"]
ms.keywords: CancelMappedTransfer, CancelMappedTransfer callback function [Kernel-Mode Driver Architecture], PCANCEL_MAPPED_TRANSFER, PCANCEL_MAPPED_TRANSFER callback, kernel.cancelmappedtransfer, wdm/CancelMappedTransfer
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
 - PCANCEL_MAPPED_TRANSFER
 - wdm/PCANCEL_MAPPED_TRANSFER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - CancelMappedTransfer
---

# PCANCEL_MAPPED_TRANSFER callback function


## -description

The <b>CancelMappedTransfer</b> routine cancels a system DMA transfer that is currently mapped to an adapter.

## -parameters

### -param DmaAdapter 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure. This structure is the adapter object that is waiting for the pending DMA transfer to complete. The caller obtained this pointer from a previous call to the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> routine, and the caller passed this pointer to the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer_ex">MapTransferEx</a> call that set up the map registers for the DMA transfer.

### -param DmaTransferContext 

[in]
A pointer to a DMA transfer context. This parameter value must be the same DMA transfer context that was passed to the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel_ex">AllocateAdapterChannelEx</a> call that requested the adapter channel allocation.

## -returns

<b>CancelMappedTransfer</b> returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.

## -remarks

<b>CancelMappedTransfer</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

This routine marks the associated transfer context as canceled, which prevents any further transfers under this context. After a transfer is canceled, its completion routine is called, but the status for the transfer might be set to <b>DmaCancelled</b>.

Regardless of whether a system DMA transfer is canceled or completed, the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pflush_adapter_buffers">FlushAdapterBuffers</a> or <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pflush_adapter_buffers_ex">FlushAdapterBuffersEx</a> routine must always be called to flush any data that remains in the system DMA controller's internal cache at the end of a DMA transfer operation. After the transfer is canceled or completed, the <b>FlushAdapterBuffers<i>Xxx</i></b> call must occur before either the DMA channel is released or the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer_ex">MapTransferEx</a> routine is called to set up the map registers for a new DMA transfer.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel_ex">AllocateAdapterChannelEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pflush_adapter_buffers">FlushAdapterBuffers</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pflush_adapter_buffers_ex">FlushAdapterBuffersEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pinitialize_dma_transfer_context">InitializeDmaTransferContext</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer_ex">MapTransferEx</a>
