---
UID: NC:wdm.PCALCULATE_SCATTER_GATHER_LIST_SIZE
title: PCALCULATE_SCATTER_GATHER_LIST_SIZE (wdm.h)
description: The CalculateScatterGatherList routine calculates the size, in bytes, of scatter/gather list necessary to hold a given buffer.
old-location: kernel\calculatescattergatherlist.htm
tech.root: kernel
ms.assetid: d7509502-0965-44b9-8efb-cec4fbe3ac88
ms.date: 04/30/2018
keywords: ["PCALCULATE_SCATTER_GATHER_LIST_SIZE callback function"]
ms.keywords: CalculateScatterGatherList, CalculateScatterGatherList callback function [Kernel-Mode Driver Architecture], PCALCULATE_SCATTER_GATHER_LIST_SIZE, PCALCULATE_SCATTER_GATHER_LIST_SIZE callback, kdma_f2e8ba68-4b5d-4a3c-9e81-1bf84cc7cc48.xml, kernel.calculatescattergatherlist, wdm/CalculateScatterGatherList
f1_keywords:
 - "wdm/CalculateScatterGatherList"
 - "CalculateScatterGatherList"
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wdm.h
api_name:
- CalculateScatterGatherList
targetos: Windows
req.typenames: 
---

# PCALCULATE_SCATTER_GATHER_LIST_SIZE callback function


## -description


The <b>CalculateScatterGatherList</b> routine calculates the size, in bytes, of scatter/gather list necessary to hold a given buffer.


## -parameters




### -param DmaAdapter 
[in]
Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.


### -param Mdl 
[in, optional]
Either <b>NULL</b> or a pointer to the MDL that contains the buffer. 


### -param CurrentVa 
[in]
Pointer to the virtual address of the beginning of the buffer. 


### -param Length 
[in]
Specifies the length of the buffer, in bytes. 


### -param ScatterGatherListSize 
[out]
Pointer to the variable the routine uses to return the size of the scatter/gather list, in bytes.


### -param pNumberOfMapRegisters








#### - NumberOfMapRegisters [out, optional]

Either <b>NULL</b> or pointer to the variable the routine uses to return the number of map registers needed for DMA operations on the buffer. 


## -returns



<b>CalculateScatterGatherList</b> returns one of the following status codes.

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
The values returned in <i>ScatterGatherListSize</i> and <i>NumberOfMapRegisters</i> are valid. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The number of map registers required exceeds the number of map registers available. 

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



<b>CalculateScatterGatherList</b>
      is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>
      structure. Drivers obtain the address of this routine by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION2. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

If the caller passes <b>NULL</b> for the <i>Mdl</i> parameter, the routine calculates the maximum possible size needed to hold a scatter/gather list for the specified buffer. If the caller specifies the MDL that contains the buffer in the <i>Mdl</i> parameter, the routine computes the actual size needed to hold the scatter/gather list.

A driver uses <b>CalculateScatterGatherList</b> to allocate a scatter/gather list buffer to pass to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pbuild_scatter_gather_list">BuildScatterGatherList</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pbuild_scatter_gather_list">BuildScatterGatherList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_description">DEVICE_DESCRIPTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a>
 

 

