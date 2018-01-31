---
UID: NC:wdm.PCANCEL_MAPPED_TRANSFER
title: PCANCEL_MAPPED_TRANSFER
author: windows-driver-content
description: The CancelMappedTransfer routine cancels a system DMA transfer that is currently mapped to an adapter.
old-location: kernel\cancelmappedtransfer.htm
old-project: kernel
ms.assetid: 12ED94F4-70A9-4716-91CD-F561F0D4D4EA
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.cancelmappedtransfer, CancelMappedTransfer, CancelMappedTransfer callback function [Kernel-Mode Driver Architecture], CancelMappedTransfer, PCANCEL_MAPPED_TRANSFER, PCANCEL_MAPPED_TRANSFER, wdm/CancelMappedTransfer
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	CancelMappedTransfer
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PCANCEL_MAPPED_TRANSFER callback


## -description


The <b>CancelMappedTransfer</b> routine cancels a system DMA transfer that is currently mapped to an adapter.


## -prototype


````
PCANCEL_MAPPED_TRANSFER CancelMappedTransfer;

NTSTATUS CancelMappedTransfer(
  _In_ PDMA_ADAPTER DmaAdapter,
  _In_ PVOID        DmaTransferContext
)
{ ... }
````


## -parameters




#### - DmaAdapter [in]

A pointer to a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure. This structure is the adapter object that is waiting for the pending DMA transfer to complete. The caller obtained this pointer from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine, and the caller passed this pointer to the <a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a> call that set up the map registers for the DMA transfer.


#### - DmaTransferContext [in]

A pointer to a DMA transfer context. This parameter value must be the same DMA transfer context that was passed to the <a href="..\wdm\nc-wdm-pallocate_adapter_channel_ex.md">AllocateAdapterChannelEx</a> call that requested the adapter channel allocation.


## -returns


<b>CancelMappedTransfer</b> returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.



## -remarks


<b>CancelMappedTransfer</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

This routine marks the associated transfer context as canceled, which prevents any further transfers under this context. After a transfer is canceled, its completion routine is called, but the status for the transfer might be set to <b>DmaCancelled</b>.

Regardless of whether a system DMA transfer is canceled or completed, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a> or <a href="..\wdm\nc-wdm-pflush_adapter_buffers_ex.md">FlushAdapterBuffersEx</a> routine must always be called to flush any data that remains in the system DMA controller's internal cache at the end of a DMA transfer operation. After the transfer is canceled or completed, the <b>FlushAdapterBuffers<i>Xxx</i></b> call must occur before either the DMA channel is released or the <a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a> routine is called to set up the map registers for a new DMA transfer.



## -see-also

<a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a>

<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>

<a href="..\wdm\nc-wdm-pinitialize_dma_transfer_context.md">InitializeDmaTransferContext</a>

<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>

<a href="..\wdm\nc-wdm-pallocate_adapter_channel_ex.md">AllocateAdapterChannelEx</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a>

<a href="..\wdm\nc-wdm-pflush_adapter_buffers_ex.md">FlushAdapterBuffersEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCANCEL_MAPPED_TRANSFER callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

