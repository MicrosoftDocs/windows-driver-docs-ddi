---
UID: NS:d3d12umddi.D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020
title: D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020 (d3d12umddi.h)
description: Specifies output stream parameters for the output to be processed.
old-location: display\d3d12ddiarg_video_process_output_stream_parameters.htm
ms.date: 12/09/2021
keywords: ["D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020 structure"]
ms.keywords: D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020, D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020 structure [Display Devices], d3d12umddi/D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020, display.d3d12ddiarg_video_process_output_stream_parameters
f1_keywords:
 - "d3d12umddi/D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020"
 - "D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020"
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
req.max-support: Windows 10, version 1709
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
- D3d12umddi.h
api_name:
- D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020
targetos: Windows
tech.root: display
req.typenames: D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020
---

# D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020 structure

## -description

**D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020** specifies output stream parameters for the output to be processed.

## -struct-fields

### -field OutputStream

The output surfaces for the video process command. If stereo output is enabled, index 0 contains the left output while index 1 contains the right input. If stereo output is not enabled, only index 0 is used to specify the output. Index 1 should be a null pointer.

### -field AlphaFillMode

The alpha fill mode for data that the video processor writes to the render target.  For more information, see [**D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE**](ne-d3d12umddi-d3d12ddi_video_process_alpha_fill_mode_0020.md) enumeration.

### -field AlphaFillModeSourceStreamIndex

The zero-based index of an input stream. If the **AlphaFillMode** member has the value **D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_SOURCE_STREAM**, this value is used. Otherwise, it is ignored.

### -field BackgroundColor

The background color, which the video processor uses to fill areas of the target rectangle that do not contain a video image. Areas outside the target rectangle are not affected.  The meaning of the values are specified by the **ColorSpace** member

|     | YCbCrA | RGBA |
| --- | ------ | ---- |
|BackgroundColor[0] | Y  |R|
|BackgroundColor[1] | Cb |G|
|BackgroundColor[2] | Cr |N|
|BackgroundColor[3] | A  |A|

### -field FrameRate

The frame rate of the output video stream, specified as a [**DXGI_RATIONAL**](/windows/win32/api/dxgicommon/ns-dxgicommon-dxgi_rational) structure.

### -field EnableStereo

If true, stereo output is enabled. If false, the video processor produces mono video frames.

### -field ColorSpace

The color space for the video processor output surface as a [**DXGI_COLOR_SPACE_TYPE**](/windows/win32/api/dxgicommon/ne-dxgicommon-dxgi_color_space_type) value.

### -field TargetRectangle

The target rectangle, which is the area within the destination surface where the output is drawn. The target rectangle is given in pixel coordinates, relative to the destination surface.

## -see-also

[**D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE**](ne-d3d12umddi-d3d12ddi_video_process_alpha_fill_mode_0020.md)

[**DXGI_COLOR_SPACE_TYPE**](/windows/win32/api/dxgicommon/ne-dxgicommon-dxgi_color_space_type)

[**DXGI_RATIONAL**](/windows/win32/api/dxgicommon/ns-dxgicommon-dxgi_rational)
