---
UID: NS:d3dkmddi._DXGKARG_RENDERGDI
title: _DXGKARG_RENDERGDI (d3dkmddi.h)
description: The DXGKARG_RENDERGDI structure is used when submitting Windows Graphics Device Interface (GDI) commands for contexts that support virtual addressing.
old-location: display\dxgkarg_rendergdi.htm
ms.assetid: E1DC536B-581E-43F8-99B2-776DC30EEBB7
ms.date: 05/10/2018
keywords: ["_DXGKARG_RENDERGDI structure"]
ms.keywords: "*INOUT_PDXGKARG_RENDERGDI, DXGKARG_RENDERGDI, DXGKARG_RENDERGDI structure [Display Devices], _DXGKARG_RENDERGDI, d3dkmddi/DXGKARG_RENDERGDI, display.dxgkarg_rendergdi"
f1_keywords:
 - "d3dkmddi/DXGKARG_RENDERGDI"
 - "DXGKARG_RENDERGDI"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- d3dkmddi.h
api_name:
- DXGKARG_RENDERGDI
targetos: Windows
tech.root: display
req.typenames: DXGKARG_RENDERGDI
---

# _DXGKARG_RENDERGDI structure


## -description


The <b>DXGKARG_RENDERGDI</b> structure is used when submitting Windows Graphics Device Interface (GDI) commands for contexts that support virtual addressing.


## -struct-fields




### -field pCommand

A pointer to the start of the command buffer.


### -field CommandLength

The size, in bytes, of the command buffer that <b>pCommand</b> points to.


### -field pDmaBuffer

A pointer to the start of the DMA buffer, which is aligned on 4 KB. 


### -field DmaBufferGpuVirtualAddress

A <b>D3DGPU_VIRTUAL_ADDRESS</b> data type that indicates the virtual address where the DMA buffer was paged in. If the physical address is zero, the DMA buffer is not correctly paged in.


### -field DmaSize

The size, in bytes, of the DMA buffer that <b>pDmaBuffer</b> points to.


### -field pDmaBufferPrivateData

A pointer to a driver-resident private data structure that is used for generating the DMA buffer that <b>pDmaBuffer</b> points to.


### -field DmaBufferPrivateDataSize

The number of bytes that remain in the private data structure that <b>pDmaBufferPrivateData</b> points to for the current operation.


### -field pAllocationList

An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationlist">DXGK_ALLOCATIONLIST</a> structures for the list of allocations that the DMA buffer references. Each allocation that is referenced should appear once for optimal performance.


### -field AllocationListSize

The available number of elements in the array that <b>pAllocationList</b> specifies, which represents the number of allocation specifications to send through DMA to the graphics hardware.


### -field MultipassOffset

A value that specifies the progress of the rendering operation.

