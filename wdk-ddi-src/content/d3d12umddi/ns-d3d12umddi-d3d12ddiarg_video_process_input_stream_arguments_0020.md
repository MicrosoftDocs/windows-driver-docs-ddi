---
UID: NS:d3d12umddi.D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020
title: D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020 (d3d12umddi.h)
description: Specifies input stream parameters for an input stream passed to the pfnProcessFrame callback function.
old-location: display\d3d12ddiarg_video_process_input_stream_parameters.htm
ms.assetid: 2488E73E-CF47-4852-8090-BC063DCC4EA4
ms.date: 05/10/2018
keywords: ["D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020 structure"]
ms.keywords: D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020, D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020 structure [Display Devices], d3d12umddi/D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020, display.d3d12ddiarg_video_process_input_stream_parameters
f1_keywords:
 - "d3d12umddi/D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020"
 - "D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020"
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
- D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020
targetos: Windows
tech.root: display
req.typenames: D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020
---

# D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020 structure


## -description


Specifies input stream parameters for an input stream passed to the pfnProcessFrame callback function.


## -struct-fields




### -field InputStream

The set of references to be able to perform processing. If stereo format is <b>D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_SEPARATE</b>, two sets of input streams must be supplied.  If stereo format is any other mode, the first set of reference must be supplied, and the second should be zero initialized.


### -field Transform

Flip, rotation, scale and destination translation for the video input.  For more information, see the <a href="https://msdn.microsoft.com/E463BD7F-F89C-4D82-ABCA-4AF48EC21655">D3D12DDI_VIDEO_PROCESS_TRANSFORM</a> structure. 


### -field Flags

Options for the input stream.  For more information, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_process_input_stream_flags_0020">D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS</a> enumeration.


### -field RateInfo

Frame rate and input and output indexes for frame rate conversion and deinterlacing.  For more information, see the <a href="https://msdn.microsoft.com/3F92B206-BA05-4ECC-854B-8D1EA9D7FD19">D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO</a> structure.


### -field FieldType

Frame format as progressive or interlaced for the input stream.


### -field DeinterlaceMode

The deinterlace mode to use.  For more information, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_process_deinterlace_flags_0020">D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS</a> enumeration.


### -field StereoFormat

Specifies whether the stream is stereo or not. If there is a value of <b>D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_SEPARATE</b>, there are two sets of input textures and references. This is to support a stereo interlaced case.


### -field ColorSpace

The color space for the video processor input and reference surfaces as a <a href="https://docs.microsoft.com/windows/win32/api/dxgicommon/ne-dxgicommon-dxgi_color_space_type">DXGI_COLOR_SPACE_TYPE</a> value.


### -field FilterFlags

The filters to enable, as a bitwise OR of one or more flags from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_process_filter_flags_0020">D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS</a> enumeration.


### -field FilterLevels

The level to apply for each enabled filter.  If a filter is not enabled or the filter index is reserved, specify zero (0).


### -field AlphaBlending

The planar alpha for an input stream on the video processor.  For more information, see the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddi_video_process_alpha_blending_0020">D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING</a> structure.


### -field LumaKey

The luma key for an input stream on the video processor.  For more information, see the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddi_video_process_luma_key_0020">D3D12DDI_VIDEO_PROCESS_LUMA_KEY</a> structure.


### -field Palette

The palette to use for this stream. If the video processor supports the given palletized formats, it must apply alpha values from color palette entries.


### -field EnableAutoProcessing

Whether to enable automatic processing features on the video processor.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddi_video_process_alpha_blending_0020">D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_process_deinterlace_flags_0020">D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_process_filter_flags_0020">D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_process_input_stream_flags_0020">D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS</a>



<a href="https://msdn.microsoft.com/3F92B206-BA05-4ECC-854B-8D1EA9D7FD19">D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddi_video_process_luma_key_0020">D3D12DDI_VIDEO_PROCESS_LUMA_KEY</a>



<a href="https://msdn.microsoft.com/E463BD7F-F89C-4D82-ABCA-4AF48EC21655">D3D12DDI_VIDEO_PROCESS_TRANSFORM</a>



<a href="https://docs.microsoft.com/windows/win32/api/dxgicommon/ne-dxgicommon-dxgi_color_space_type">DXGI_COLOR_SPACE_TYPE</a>
 

 

