---
UID: NS:wdm._DMA_TRANSFER_INFO_V2
title: _DMA_TRANSFER_INFO_V2
author: windows-driver-content
description: Contains the allocation requirements for a scatter/gather list that describes the I/O data buffer for a DMA transfer.
ms.assetid: b6466a0d-273f-4bc0-a4fe-f79fcb4ba5b6
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DMA_TRANSFER_INFO_V2, DMA_TRANSFER_INFO_V2, *PDMA_TRANSFER_INFO_V2, 
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DMA_TRANSFER_INFO_V2, *PDMA_TRANSFER_INFO_V2
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	wdm.h
api_name: 
-	_DMA_TRANSFER_INFO_V2
product: Windows
targetos: Windows
---

# _DMA_TRANSFER_INFO_V2 structure

## -description
Contains the allocation requirements for a scatter/gather list that describes the I/O data buffer for a DMA transfer.

## -struct-fields

### -field MapRegisterCount

The number of map registers required to translate all the physical addresses in the scatter/gather list to logical addresses.


### -field ScatterGatherElementCount

The number of scatter/gather elements in the scatter/gather list. Each element is a structure of type <b>SCATTER_GATHER_ELEMENT</b>.


### -field ScatterGatherListSize

The required size, in bytes, of the scatter/gather buffer. This buffer contains the scatter/gather list that describes the memory that is used to buffer I/O data during the DMA transfer. The scatter/gather buffer must be large enough to contain a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563664">SCATTER_GATHER_LIST</a> structure and an array of <b>SCATTER_GATHER_ELEMENT</b> structures, plus additional data that is used internally by the operating system.

### -field LogicalPageCount
The number of logical pages.

## -remarks

The <b>V2</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451001">DMA_TRANSFER_INFO</a> structure is a structure of type <b>DMA_TRANSFER_INFO_V2</b>.

The <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451125">GetDmaTransferInfo</a> routine together describe the I/O data buffer for a DMA transfer. For the purpose of programming a DMA controller, this buffer can more conveniently be described by a scatter/gather list. (A scatter/gather list describes the memory in an I/O data buffer but does not contain this memory.) A driver calls <b>GetDmaTransferInfo</b> to obtain the allocation requirements for this scatter/gather list. <b>GetDmaTransferInfo</b> writes the allocation requirements into the <b>V1</b> member of a caller-supplied <b>DMA_TRANSFER_INFO</b> structure.

## -see-also