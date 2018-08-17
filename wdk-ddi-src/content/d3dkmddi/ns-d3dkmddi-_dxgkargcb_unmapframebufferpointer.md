---
UID: NS:d3dkmddi._DXGKARGCB_UNMAPFRAMEBUFFERPOINTER
title: _DXGKARGCB_UNMAPFRAMEBUFFERPOINTER
author: windows-driver-content
description:
ms.assetid: 16f1a189-7470-43ff-9b5f-15b87a120eaf
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARGCB_UNMAPFRAMEBUFFERPOINTER, DXGKARGCB_UNMAPFRAMEBUFFERPOINTER,
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
req.typenames: DXGKARGCB_UNMAPFRAMEBUFFERPOINTER
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	_DXGKARGCB_UNMAPFRAMEBUFFERPOINTER
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGKARGCB_UNMAPFRAMEBUFFERPOINTER structure

## -description

Arguments used by the [DxgkcbUnmapFrameBufferPointer](nc-d3dkmddi-dxgkcb_unmapframebufferpointer.md) callback function to release a mapping.

## -struct-fields

### -field PhysicalAdapterIndex

The index of the physical adapter.

### -field pBaseAddress

A CPU accessible base address pointer to the mapped subregion of the section object.

## -remarks

## -see-also

[DxgkcbUnmapFrameBufferPointer](nc-d3dkmddi-dxgkcb_unmapframebufferpointer.md)
