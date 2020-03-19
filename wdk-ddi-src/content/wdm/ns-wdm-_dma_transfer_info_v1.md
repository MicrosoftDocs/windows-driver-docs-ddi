---
UID: NS:wdm._DMA_TRANSFER_INFO_V1
title: _DMA_TRANSFER_INFO_V1 (wdm.h)
description: The DMA_TRANSFER_INFO_V1 structure contains the allocation requirements for a scatter/gather list that describes the I/O data buffer for a DMA transfer.
old-location: kernel\dma_transfer_info_v1.htm
tech.root: kernel
ms.assetid: 01EAF66D-F4E8-4D0F-A52C-900EF338FCA1
ms.date: 04/30/2018
keywords: ["_DMA_TRANSFER_INFO_V1 structure"]
ms.keywords: "*PDMA_TRANSFER_INFO_V1, DMA_ TRANSFER _INFO_V1, DMA_ TRANSFER _INFO_V1 structure [Kernel-Mode Driver Architecture], DMA_TRANSFER_INFO_V1, DMA_TRANSFER_INFO_V1 structure [Kernel-Mode Driver Architecture], PDMA_ TRANSFER _INFO_V1, PDMA_ TRANSFER _INFO_V1 structure pointer [Kernel-Mode Driver Architecture], _DMA_TRANSFER_INFO_V1, kernel.dma_transfer_info_v1, wdm/ DMA_ TRANSFER _INFO_V1, wdm/PDMA_ TRANSFER _INFO_V1"
f1_keywords:
 - "wdm/DMA_ TRANSFER _INFO_V1"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- DMA_ TRANSFER _INFO_V1
product:
- Windows
targetos: Windows
req.typenames: DMA_TRANSFER_INFO_V1, *PDMA_TRANSFER_INFO_V1
---

# _DMA_TRANSFER_INFO_V1 structure


## -description


The  <b>DMA_TRANSFER_INFO_V1</b> structure contains the allocation requirements for a scatter/gather list that describes the I/O data buffer for a DMA transfer.


## -struct-fields




### -field MapRegisterCount

The number of map registers required to translate all the physical addresses in the scatter/gather list to logical addresses.


### -field ScatterGatherElementCount

The number of scatter/gather elements in the scatter/gather list. Each element is a structure of type <b>SCATTER_GATHER_ELEMENT</b>.


### -field ScatterGatherListSize

The required size, in bytes, of the scatter/gather buffer. This buffer contains the scatter/gather list that describes the memory that is used to buffer I/O data during the DMA transfer. The scatter/gather buffer must be large enough to contain a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a> structure and an array of <b>SCATTER_GATHER_ELEMENT</b> structures, plus additional data that is used internally by the operating system.


## -remarks



The <b>V1</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_transfer_info">DMA_TRANSFER_INFO</a> structure is a structure of type <b>DMA_TRANSFER_INFO_V1</b>.

The <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_dma_transfer_info">GetDmaTransferInfo</a> routine together describe the I/O data buffer for a DMA transfer. For the purpose of programming a DMA controller, this buffer can more conveniently be described by a scatter/gather list. (A scatter/gather list describes the memory in an I/O data buffer but does not contain this memory.) A driver calls <b>GetDmaTransferInfo</b> to obtain the allocation requirements for this scatter/gather list. <b>GetDmaTransferInfo</b> writes the allocation requirements into the <b>V1</b> member of a caller-supplied <b>DMA_TRANSFER_INFO</b> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_transfer_info">DMA_TRANSFER_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_dma_transfer_info">GetDmaTransferInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a>
 

 

