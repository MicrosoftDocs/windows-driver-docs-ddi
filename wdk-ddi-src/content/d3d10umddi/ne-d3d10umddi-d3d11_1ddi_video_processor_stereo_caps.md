---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS (d3d10umddi.h)
description: Defines stereo 3-D capabilities for a Microsoft Direct3D 11 video processor.
old-location: display\d3d11_1ddi_video_processor_stereo_caps.htm
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS enumeration"]
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS enumeration [Display Devices], D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_CHECKERBOARD, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_COLUMN_INTERLEAVED, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_FLIP_MODE, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_MONO_OFFSET, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_ROW_INTERLEAVED, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_CHECKERBOARD, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_COLUMN_INTERLEAVED, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_FLIP_MODE, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_MONO_OFFSET, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_ROW_INTERLEAVED, display.d3d11_1ddi_video_processor_stereo_caps
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
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS
f1_keywords:
 - D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS
 - d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS
---

# D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS enumeration


## -description

Defines stereo 3-D capabilities for a Microsoft Direct3D 11 video processor.

## -enum-fields

### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_MONO_OFFSET

The video processor supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET</b> format defined in the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_format">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT</a> enumeration.

### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_ROW_INTERLEAVED

The video processor supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_ROW_INTERLEAVED</b> format.

### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_COLUMN_INTERLEAVED

The video processor supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_COLUMN_INTERLEAVED</b> 
 format.

### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_CHECKERBOARD

The video processor supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_CHECKERBOARD</b> 
format.

### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_FLIP_MODE

The video processor can flip one or both views. For more information, see <a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_flip_mode">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_flip_mode">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_format">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT</a>
