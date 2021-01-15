---
UID: NC:wdm.PGET_SCATTER_GATHER_LIST
title: PGET_SCATTER_GATHER_LIST (wdm.h)
description: The GetScatterGatherList routine prepares the system for a DMA scatter/gather operation on behalf of the target device object, through either the system DMA controller or a bus-master adapter.
old-location: kernel\getscattergatherlist.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PGET_SCATTER_GATHER_LIST callback function"]
ms.keywords: GetScatterGatherList, GetScatterGatherList callback function [Kernel-Mode Driver Architecture], PGET_SCATTER_GATHER_LIST, PGET_SCATTER_GATHER_LIST callback, kdma_b451cb34-7181-4272-a1ef-0c8fc233a7fd.xml, kernel.getscattergatherlist, ntddk/GetScatterGatherList
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
 - PGET_SCATTER_GATHER_LIST
 - wdm/PGET_SCATTER_GATHER_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ntddk.h
api_name:
 - PGET_SCATTER_GATHER_LIST
---

# PGET_SCATTER_GATHER_LIST callback function


## -description

The <b>GetScatterGatherList</b> routine prepares the system for a DMA scatter/gather operation on behalf of the target device object, through either the system DMA controller or a bus-master adapter.

## -parameters

### -param DmaAdapter 

[in]
Pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure returned by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.

### -param DeviceObject 

[in]
Pointer to the device object that represents the target device for the DMA operation.

### -param Mdl 

[in]
Pointer to the MDL that describes the buffer at <i>MdlAddress</i> in the current IRP.

### -param CurrentVa 

[in]
Pointer to the current virtual address in the MDL for the buffer to be mapped for a DMA transfer operation.

### -param Length 

[in]
Specifies the length, in bytes, to be mapped.

### -param ExecutionRoutine 

[in]
Pointer to a driver-supplied <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_list_control">AdapterListControl</a> routine, which is called at DISPATCH_LEVEL when the system DMA controller or bus-master adapter is available.

### -param Context 

[in]
Pointer to the driver-determined context passed to the driver's <i>AdapterListControl</i> routine when it is called.

### -param WriteToDevice 

[in]
Indicates the direction of the DMA transfer: <b>TRUE</b> for a transfer from the buffer to the device, and <b>FALSE</b> otherwise.

## -returns

This routine can return one of the following NTSTATUS values. 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The routine could not allocate sufficient memory or the number of map registers required for the transfer is larger than the value returned by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer is too small for the requested transfer.

</td>
</tr>
</table>

## -remarks

The <b>GetScatterGatherList</b> routine dynamically allocates a buffer to hold the scatter/gather list. For possible NTSTATUS values if the buffer allocation fails, see the return value.

<b>GetScatterGatherList</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>.

As soon as the appropriate DMA channel and any necessary map registers are available, <b>GetScatterGatherList</b> creates a scatter/gather list, initializes the map registers, and then calls the driver-supplied <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_list_control">AdapterListControl</a> routine to carry out the I/O operation.

<b>GetScatterGatherList</b> combines the actions of the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel">AllocateAdapterChannel</a> and <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer">MapTransfer</a> routines for drivers that perform scatter/gather DMA. <b>GetScatterGatherList</b> determines how many map registers are required for the transfer, allocates the map registers, maps the buffers for DMA, and fills in the scatter/gather list. It then calls the supplied <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_list_control">AdapterListControl</a> routine, passing a pointer to the scatter/gather list in <i>ScatterGather</i>. The driver should retain this pointer for use when calling <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pput_scatter_gather_list">PutScatterGatherList</a>. Note that <b>GetScatterGatherList</b> does not have the queuing restrictions that apply to <b>AllocateAdapterChannel</b>.

In its <i>AdapterListControl</i> routine, the driver should perform the I/O. On return from the driver-supplied routine, <b>GetScatterGatherList</b> keeps the map registers but frees the DMA adapter structure. The driver must call <b>PutScatterGatherList</b> (which flushes the buffers) before it can access the data in the buffer.

This routine can handle chained MDLs, provided that the total number of map registers required by all chained MDLs does not exceed the number of map registers that are available.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel">AllocateAdapterChannel</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pput_scatter_gather_list">PutScatterGatherList</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a>

