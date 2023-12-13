---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032
title: D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032 (d3d12umddi.h)
description: Learn more about the D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032 structure.
ms.date: 12/08/2023
keywords: ["D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032 structure"]
ms.keywords: D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032, D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032, display.d3d12ddi_video_process_output_stream_desc_0032
req.header: d3d12umddi.h
req.include-header: 
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
req.typenames: D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032
f1_keywords:
 - D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032
 - d3d12umddi/D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032
---

# D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032 structure

## -description

**D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032** describes output stream properties for the video processor.

## -struct-fields

### -field Format

The DXGI format of the output texture.

### -field ColorSpace

The color space for the video processor output surface as a [**DXGI_COLOR_SPACE_TYPE**](/windows/win32/api/dxgicommon/ne-dxgicommon-dxgi_color_space_type) value.

### -field AlphaFillMode

The alpha fill mode for data that the video processor writes to the render target. See [**D3D12DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE**](ne-d3d12umddi-d3d12ddi_video_process_alpha_fill_mode_0020.md).

### -field AlphaFillModeSourceStreamIndex

The zero-based index of an input stream. This field is used if **AlphaFillMode** has the value **D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_SOURCE_STREAM**. Otherwise, it is ignored.

### -field BackgroundColor

The video processor uses the background color to fill areas of the target rectangle that don't contain a video image. Areas outside the target rectangle aren't affected. The meaning of the values is specified by the **ColorSpace** member.

| Value | YCbCrA | RGBA |
| ----- | ------ | ---- |
| BackgroundColor[0] | Y | R |
| BackgroundColor[1] | Cb | G |
| BackgroundColor[2] | Cr | B |
| BackgroundColor[3] | A | A |

### -field FrameRate

The frame rate of the output video stream, specified as a [**DXGI_RATIONAL**](/windows/win32/api/dxgicommon/ns-dxgicommon-dxgi_rational) structure.

### -field EnableStereo

If TRUE, stereo output is enabled. Otherwise, the video processor produces mono video frames.

## -see-also

[**PFND3D12DDI_VIDEO_PROCESS_FRAME_0043**](nc-d3d12umddi-pfnd3d12ddi_video_process_frame_0043.md)
