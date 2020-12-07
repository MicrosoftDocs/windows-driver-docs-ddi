---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_COLOR
title: D3D11_1DDI_VIDEO_COLOR (d3d10umddi.h)
description: Defines a color value for Microsoft Direct3D 11 video.
old-location: display\d3d11_1ddi_video_color.htm
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_VIDEO_COLOR structure"]
ms.keywords: D3D11_1DDI_VIDEO_COLOR, D3D11_1DDI_VIDEO_COLOR structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_COLOR, display.d3d11_1ddi_video_color
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: D3D11_1DDI_VIDEO_COLOR
f1_keywords:
 - D3D11_1DDI_VIDEO_COLOR
 - d3d10umddi/D3D11_1DDI_VIDEO_COLOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1DDI_VIDEO_COLOR
---

# D3D11_1DDI_VIDEO_COLOR structure


## -description

Defines a color value for Microsoft Direct3D 11 video.

## -struct-fields

### -field YCbCr

A <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_color_ycbcra">D3D11_1DDI_VIDEO_COLOR_YCbCrA</a> structure that contains a YCbCr color value.

### -field RGBA

A <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_color_rgba">D3D11_1DDI_VIDEO_COLOR_RGBA</a> structure that contains an RGB color value.

## -remarks

The anonymous union can represent both RGB and YCbCr colors. The interpretation of the union depends on the context.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_color_rgba">D3D11_1DDI_VIDEO_COLOR_RGBA</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_color_ycbcra">D3D11_1DDI_VIDEO_COLOR_YCbCrA</a>
