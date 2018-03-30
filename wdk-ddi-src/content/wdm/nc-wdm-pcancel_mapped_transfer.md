---
UID: NC:wdm.PCANCEL_MAPPED_TRANSFER
title: PCANCEL_MAPPED_TRANSFER
author: windows-driver-content
description: The CancelMappedTransfer routine cancels a system DMA transfer that is currently mapped to an adapter.
old-location: kernel\cancelmappedtransfer.htm
old-project: kernel
ms.assetid: 12ED94F4-70A9-4716-91CD-F561F0D4D4EA
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: CancelMappedTransfer, CancelMappedTransfer callback function [Kernel-Mode Driver Architecture], PCANCEL_MAPPED_TRANSFER, kernel.cancelmappedtransfer, wdm/CancelMappedTransfer
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
-	CancelMappedTransfer
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PCANCEL_MAPPED_TRANSFER callback


## -description


The <b>CancelMappedTransfer</b> routine cancels a system DMA transfer that is currently mapped to an adapter.


## -parameters




### -param DmaAdapter [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure. This structure is the adapter object that is waiting for the pending DMA transfer to complete. The caller obtained this pointer from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine, and the caller passed this pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406521">MapTransferEx</a> call that set up the map registers for the DMA transfer.


### -param DmaTransferContext [in]

A pointer to a DMA transfer context. This parameter value must be the same DMA transfer context that was passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406340">AllocateAdapterChannelEx</a> call that requested the adapter channel allocation.


## -returns



<b>CancelMappedTransfer</b> returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.




## -remarks



<b>CancelMappedTransfer</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

This routine marks the associated transfer context as canceled, which prevents any further transfers under this context. After a transfer is canceled, its completion routine is called, but the status for the transfer might be set to <b>DmaCancelled</b>.

Regardless of whether a system DMA transfer is canceled or completed, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/hh451102">FlushAdapterBuffersEx</a> routine must always be called to flush any data that remains in the system DMA controller's internal cache at the end of a DMA transfer operation. After the transfer is canceled or completed, the <b>FlushAdapterBuffers<i>Xxx</i></b> call must occur before either the DMA channel is released or the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406521">MapTransferEx</a> routine is called to set up the map registers for a new DMA transfer.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406340">AllocateAdapterChannelEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451102">FlushAdapterBuffersEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451191">InitializeDmaTransferContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406521">MapTransferEx</a>
 

 

