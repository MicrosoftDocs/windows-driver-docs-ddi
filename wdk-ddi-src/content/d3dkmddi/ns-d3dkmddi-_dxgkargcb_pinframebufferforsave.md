---
UID: NS:d3dkmddi._DXGKARGCB_PINFRAMEBUFFERFORSAVE
title: _DXGKARGCB_PINFRAMEBUFFERFORSAVE
author: windows-driver-content
description: Arguments used by the DxgkcbPinFrameBufferForSave callback function, to pin frame buffer for save.
ms.assetid: 7c151074-7ac1-42b2-84ae-78ae67087b44
ms.date:
ms.topic: struct
ms.keywords: _DXGKARGCB_PINFRAMEBUFFERFORSAVE, DXGKARGCB_PINFRAMEBUFFERFORSAVE, *INOUT_PDXGKARGCB_PINFRAMEBUFFERFORSAVE
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
req.typenames: DXGKARGCB_PINFRAMEBUFFERFORSAVE
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	_DXGKARGCB_PINFRAMEBUFFERFORSAVE
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGKARGCB_PINFRAMEBUFFERFORSAVE structure

## -description

Arguments used by the [DxgkcbPinFrameBufferForSave](C:\drivers\wdk-ddi\wdk-ddi-src\content\d3dkmddi\nc-d3dkmddi-dxgkcb_pinframebufferforsave.md) callback function, to pin frame buffer for save.

## -struct-fields

### -field PhysicalAdapterIndex

The index of the physical adapter.

### -field CommitSize

The size, in bytes, which the driver requires to pin. This size must be a multiple of PAGE_SIZE and must be less than or equal to the maximum size specified by the driver during initialization in DXGK_FRAMEBUFFERSAVEAREA (during DXGKQAITYPE_FRAMEBUFFERSAVESIZE).

### -field pMdl

An MDL pointing to the pages of the frame buffer save area. These pages are guaranteed to be mapped to the IoMmu.

## -remarks

## -see-also

[DxgkcbPinFrameBufferForSave](C:\drivers\wdk-ddi\wdk-ddi-src\content\d3dkmddi\nc-d3dkmddi-dxgkcb_pinframebufferforsave.md)
