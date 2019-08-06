---
UID: NC:wdm.PGET_DMA_ADAPTER_INFO
title: PGET_DMA_ADAPTER_INFO (wdm.h)
description: The GetDmaAdapterInfo routine retrieves information about the hardware capabilities of a system DMA channel.
old-location: kernel\getdmaadapterinfo.htm
tech.root: kernel
ms.assetid: 2F502ACA-0CFF-46A1-B54C-1034D6E56815
ms.date: 04/30/2018
ms.keywords: GetDmaAdapterInfo, GetDmaAdapterInfo callback function [Kernel-Mode Driver Architecture], PGET_DMA_ADAPTER_INFO, PGET_DMA_ADAPTER_INFO callback, kernel.getdmaadapterinfo, wdm/GetDmaAdapterInfo
ms.topic: callback
f1_keywords:
 - "wdm/GetDmaAdapterInfo"
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
- GetDmaAdapterInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# PGET_DMA_ADAPTER_INFO callback function


## -description


The <b>GetDmaAdapterInfo</b> routine retrieves information about the hardware capabilities of a system DMA channel.


## -parameters




### -param DmaAdapter [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's system DMA channel. The caller obtained this pointer from a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> routine.


### -param AdapterInfo [in, out]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_adapter_info">DMA_ADAPTER_INFO</a> structure. The routine writes information about the system DMA controller into this structure. The caller must set the
        <b>Version</b> member of this structure to DMA_ADAPTER_INFO_VERSION1 before calling <b>GetDmaAdapterInfo</b>.


## -returns



<b>GetDmaAdapterInfo</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The routine does not support the specified version of the <b>DMA_ADAPTER_INFO_<i>XXX</i></b> structure.

</td>
</tr>
</table>
 




## -remarks



<b>GetDmaAdapterInfo</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

<b>GetDmaAdapterInfo</b> retrieves the following information:

<ul>
<li>
The maximum number of elements in a scatter/gather list that the DMA controller can process in a single scatter/gather DMA operation.

</li>
<li>
The width, in bits, of a DMA address.

</li>
</ul>
For information about the DMA adapter information that is provided by version 1 of the <b>DMA_ADAPTER_INFO_<i>XXX</i></b> structure, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_adapter_info_v1">DMA_ADAPTER_INFO_V1</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_adapter_info">DMA_ADAPTER_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>
 

 

