---
UID: NS:d3dkmddi._DXGKARGCB_MAPFRAMEBUFFERPOINTER
title: _DXGKARGCB_MAPFRAMEBUFFERPOINTER
author: windows-driver-content
description: Contains arguments used by the DxgkCbMapFrameBufferPointer callback function to map frame buffer pointer.
ms.assetid: 8404fc1c-84e7-4758-90cd-39de1d4320f7
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARGCB_MAPFRAMEBUFFERPOINTER, DXGKARGCB_MAPFRAMEBUFFERPOINTER, *INOUT_PDXGKARGCB_MAPFRAMEBUFFERPOINTER
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGKARGCB_MAPFRAMEBUFFERPOINTER
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	_DXGKARGCB_MAPFRAMEBUFFERPOINTER
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGKARGCB_MAPFRAMEBUFFERPOINTER structure

## -description

Contains arguments used by the [DxgkCbMapFrameBufferPointer](nc-d3dkmddi-dxgkcb_mapframebufferpointer.md) callback function to map frame buffer pointer.

## -struct-fields

### -field PhysicalAdapterIndex

The index of the physical adapter.

### -field Size

The size, in bytes, of the mapped subregion of the section object. Size must be a multiple of PAGE_SIZE.

### -field Offset

On Input, this is the offset, in bytes, to the mapped subregion of the section object. Offset must be a multiple of PAGE_SIZE. On output, this is the offset from the output base address to which the driver should copy the data.

### -field pBaseAddress

A CPU accessible base address pointer to the mapped subregion of the section object. The driver must add the output Offset value to the base address to get the destination address of any copy operations (pDestinationAddress = pBaseAddress + Offset).


## -see-also

[DxgkCbMapFrameBufferPointer](nc-d3dkmddi-dxgkcb_mapframebufferpointer.md)
