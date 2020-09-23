---
UID: NC:wdm.PMAP_TRANSFER
title: PMAP_TRANSFER (wdm.h)
description: The MapTransfer routine sets up map registers for an adapter object to map a DMA transfer from a locked-down buffer.
old-location: kernel\maptransfer.htm
tech.root: kernel
ms.assetid: 50126ab8-3094-497e-96f8-e41255d275e3
ms.date: 04/30/2018
keywords: ["PMAP_TRANSFER callback function"]
ms.keywords: MapTransfer, MapTransfer callback function [Kernel-Mode Driver Architecture], PMAP_TRANSFER, PMAP_TRANSFER callback, kdma_4bc30c1d-1d83-424f-9c58-cd92c5e9d331.xml, kernel.maptransfer, wdm/MapTransfer
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch
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
 - PMAP_TRANSFER
 - wdm/PMAP_TRANSFER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - MapTransfer
---

# PMAP_TRANSFER callback function


## -description

The <b>MapTransfer</b> routine sets up map registers for an adapter object to map a DMA transfer from a locked-down buffer.

## -parameters

### -param DmaAdapter 

[in]
Pointer to the DMA adapter object returned by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> and previously passed to <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel">AllocateAdapterChannel</a> for the current IRP's transfer request.

### -param Mdl 

[in]
Pointer to one of the following: the MDL that describes the buffer at <b>MdlAddress</b> in the current IRP or the MDL that describes the common buffer set up by the driver of a subordinate device (auto-initialize mode).

### -param MapRegisterBase 

[in]
Specifies the map registers allocated for the DMA operation.  The system passes this value  to the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_control">AdapterControl</a> routine.

### -param CurrentVa 

[in]
Pointer to the current virtual address of the data to be transferred for a DMA transfer operation.

### -param Length 

[in, out]
Specifies the length, in bytes, to be mapped. If the driver indicated that its device was a bus master with scatter/gather support when it called <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>, the value of <i>Length</i> on return from <b>MapTransfer</b> indicates how many bytes were mapped. Otherwise, the input and output values of <i>Length</i> are identical.

### -param WriteToDevice 

[in]
Indicates the direction of the transfer operation: <b>TRUE</b> for a transfer from the locked-down buffer to the device.

## -returns

<b>MapTransfer</b> returns the logical address of the region mapped, which the driver of a bus-master adapter can use. Drivers of devices that use a system DMA controller cannot use this value and should ignore it.

## -remarks

<b>MapTransfer</b><u> is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          </u><a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a><u> structure</u>. Drivers obtain the address of this routine by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>. 

The <i>DmaAdapter</i> must have already been allocated as a result of the driver's preceding call to <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel">AllocateAdapterChannel</a>.

The number of map registers that can be set up cannot exceed the maximum returned when the driver called <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>.

A driver can get the initial <i>CurrentVa</i> for the start of a packet-based DMA transfer by calling <a href="/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetMdlVirtualAddress</a>. However, the value returned is an index into the <i>Mdl</i>, rather than a valid virtual address. If the driver must split a large transfer request into more than one DMA operation, it must update <i>CurrentVa</i> and <i>Length</i> for each DMA operation.

The driver of a bus-master device with scatter/gather support can use the returned logical address and updated <i>Length</i> value to build a scatter/gather list, calling <b>MapTransfer</b> repeatedly until it has used all available map registers for the transfer operation. However, such a driver could more simply use the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list">GetScatterGatherList</a> routine.

## -see-also

<a href="/windows-hardware/drivers/kernel/mm-bad-pointer">ADDRESS_AND_SIZE_TO_SPAN_PAGES</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel">AllocateAdapterChannel</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_common_buffer">AllocateCommonBuffer</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pflush_adapter_buffers">FlushAdapterBuffers</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pfree_adapter_channel">FreeAdapterChannel</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pfree_map_registers">FreeMapRegisters</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keflushiobuffers">KeFlushIoBuffers</a>



<a href="/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetMdlVirtualAddress</a>