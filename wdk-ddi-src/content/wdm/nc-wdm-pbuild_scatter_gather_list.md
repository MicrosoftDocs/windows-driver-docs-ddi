---
UID: NC:wdm.PBUILD_SCATTER_GATHER_LIST
title: PBUILD_SCATTER_GATHER_LIST (wdm.h)
description: The BuildScatterGatherList routine prepares the system for a DMA operation, using a driver-supplied buffer to build the scatter/gather list.
old-location: kernel\buildscattergatherlist.htm
tech.root: kernel
ms.assetid: 678b568a-2efe-443e-89f5-84d012431755
ms.date: 04/30/2018
ms.keywords: BuildScatterGatherList, BuildScatterGatherList callback function [Kernel-Mode Driver Architecture], PBUILD_SCATTER_GATHER_LIST, PBUILD_SCATTER_GATHER_LIST callback, kdma_cea6dde1-9a1d-4ffb-ac0d-d8a2b658b666.xml, kernel.buildscattergatherlist, wdm/BuildScatterGatherList
f1_keywords:
 - "wdm/BuildScatterGatherList"
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wdm.h
api_name:
- BuildScatterGatherList
product:
- Windows
targetos: Windows
req.typenames: 
---

# PBUILD_SCATTER_GATHER_LIST callback function


## -description


The <b>BuildScatterGatherList</b> routine prepares the system for a DMA operation, using a driver-supplied buffer to build the scatter/gather list.


## -parameters




### -param DmaAdapter [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.


### -param DeviceObject [in]

Pointer to the device object that represents the target device for the DMA operation.


### -param Mdl [in]

Pointer to the MDL that describes the buffer specified by the <b>MdlAddress</b> member of the current IRP.


### -param CurrentVa [in]

Pointer to the current virtual address in the MDL for the buffer to be mapped for a DMA transfer operation.


### -param Length [in]

Specifies the length, in bytes, of the buffer to be mapped.


### -param ExecutionRoutine [in]

Pointer to a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_list_control">AdapterListControl</a> routine, which is called at IRQL = DISPATCH_LEVEL when the system DMA controller or bus-master adapter is available.


### -param Context [in]

Pointer to the driver-determined context passed to <i>ExecutionRoutine</i> when it is called.


### -param WriteToDevice [in]

Indicates the direction of the DMA transfer: <b>TRUE</b> for a transfer from the buffer to the device, and <b>FALSE</b> otherwise.


### -param ScatterGatherBuffer [in]

Pointer to the caller-supplied buffer that the routine fills with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a> structure.


### -param ScatterGatherLength








#### - ScatterGatherBufferLength [in]

Specifies the size, in bytes, of the buffer passed in the <i>ScatterGatherBuffer</i> parameter.


## -returns



<b>BuildScatterGatherList</b> returns one of the following values:

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
The operation is completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The system has insufficient map registers available for the transfer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>Length</i> is too big to fit within the buffer. 

</td>
</tr>
</table>
 




## -remarks



<b>BuildScatterGatherList</b>
           is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a 
          <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION2. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

<b>BuildScatterGatherList</b> performs the same operation as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list">GetScatterGatherList</a>, except that it uses the buffer supplied in the <i>ScatterGatherBuffer</i> parameter to hold the scatter/gather list that it creates. In contrast, <b>GetScatterGatherList</b> dynamically allocates a buffer to hold the scatter/gather list. If insufficient memory is available to allocate the buffer, <b>GetScatterGatherList</b> can fail with a STATUS_INSUFFICIENT_RESOURCES error. Drivers that must avoid this scenario can preallocate a buffer to hold the scatter/gather list, and use <b>BuildScatterGatherList</b> instead.

A driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pcalculate_scatter_gather_list_size">CalculateScatterGatherList</a> routine to determine the size of buffer to allocate to hold the scatter/gather list.

The driver should retain the pointer to the scatter/gather list in <i>ScatterGatherBuffer</i> for use when the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pput_scatter_gather_list">PutScatterGatherList</a>. The driver must call <b>PutScatterGatherList</b> (which flushes the list) before it can access the data in the list. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pbuild_mdl_from_scatter_gather_list">BuildMdlFromScatterGatherList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pcalculate_scatter_gather_list_size">CalculateScatterGatherList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_description">DEVICE_DESCRIPTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list">GetScatterGatherList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pput_scatter_gather_list">PutScatterGatherList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a>
 

 

