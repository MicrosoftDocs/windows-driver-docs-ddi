---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_PALETTE_0020
title: D3D12DDI_VIDEO_PROCESS_PALETTE_0020 (d3d12umddi.h)
description: Specifies whether the palette is enabled and an array of palette entries.
old-location: display\d3d12ddi_video_process_palette.htm
ms.date: 12/09/2021
keywords: ["D3D12DDI_VIDEO_PROCESS_PALETTE_0020 structure"]
ms.keywords: D3D12DDI_VIDEO_PROCESS_PALETTE_0020, D3D12DDI_VIDEO_PROCESS_PALETTE_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_PALETTE_0020, display.d3d12ddi_video_process_palette
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_PROCESS_PALETTE_0020
f1_keywords:
 - D3D12DDI_VIDEO_PROCESS_PALETTE_0020
 - d3d12umddi/D3D12DDI_VIDEO_PROCESS_PALETTE_0020
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_PROCESS_PALETTE_0020
---

# D3D12DDI_VIDEO_PROCESS_PALETTE_0020 structure

## -description

Specifies whether the palette is enabled and an array of palette entries.

## -struct-fields

### -field Enable

Whether palette is enabled.

### -field NumEntries

The number of elements in the **pEntries** array.

### -field pEntries

A pointer to an array of palette entries. For RGB streams, the palette entries use the **DXGI_FORMAT_B8G8R8A8** representation. For YCbCr streams, the palette entries use the **DXGI_FORMAT_AYUV** representation. For more information, see the [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format) enumeration. The caller allocates the array.

## -see-also

[**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format)
