---
UID: NC:wdm.PPUT_SCATTER_GATHER_LIST
title: PPUT_SCATTER_GATHER_LIST (wdm.h)
description: The PutScatterGatherList routine frees the previously allocated map registers and scatter/gather list used in scatter/gather DMA.
old-location: kernel\putscattergatherlist.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PPUT_SCATTER_GATHER_LIST callback function"]
ms.keywords: PPUT_SCATTER_GATHER_LIST, PPUT_SCATTER_GATHER_LIST callback, PutScatterGatherList, PutScatterGatherList callback function [Kernel-Mode Driver Architecture], kdma_0f73e6d3-bf6c-4f2b-aff9-ae783b2130c5.xml, kernel.putscattergatherlist, ntddk/PutScatterGatherList
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows. Not supported in Windows 98 or Windows Me.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch, IrqlDispatch(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PPUT_SCATTER_GATHER_LIST
 - wdm/PPUT_SCATTER_GATHER_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ntddk.h
api_name:
 - PutScatterGatherList
---

# PPUT_SCATTER_GATHER_LIST callback function


## -description

The <b>PutScatterGatherList</b> routine frees the previously allocated map registers and scatter/gather list used in scatter/gather DMA.

## -parameters

### -param DmaAdapter 

[in]
Pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure returned by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.

### -param ScatterGather 

[in]
Pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a> structure previously returned by <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list">GetScatterGatherList</a>.

### -param WriteToDevice 

[in]
Indicates the direction of the DMA transfer: specify <b>TRUE</b> for a transfer from the buffer to the device, and <b>FALSE</b> otherwise.

## -remarks

<b>PutScatterGatherList</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>.

Drivers should call <b>PutScatterGatherList</b> after completing scatter/gather I/O. This routine flushes the adapter buffers, frees the map registers, and unmaps and frees the associated MDLs. Additionally, the routine frees the scatter/gather list if it was previously allocated by <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list">GetScatterGatherList</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list">GetScatterGatherList</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a>
