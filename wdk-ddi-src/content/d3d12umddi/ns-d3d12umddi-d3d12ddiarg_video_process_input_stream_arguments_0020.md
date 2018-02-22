---
UID: NS:d3d12umddi.D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020
title: D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020
author: windows-driver-content
description: Specifies input stream parameters for an input stream passed to the pfnProcessFrame callback function.
old-location: display\d3d12ddiarg_video_process_input_stream_parameters.htm
old-project: display
ms.assetid: 2488E73E-CF47-4852-8090-BC063DCC4EA4
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: d3d12umddi/D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020, D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020 structure [Display Devices], D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020, display.d3d12ddiarg_video_process_input_stream_parameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020
---

# D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020 structure


## -description


Specifies input stream parameters for an input stream passed to the pfnProcessFrame callback function.


## -syntax


````
typedef struct D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020 {
  D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020           InputStream[2];
  D3D12DDI_VIDEO_PROCESS_TRANSFORM_0020              Transform;
  D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020     Flags;
  D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020 RateInfo;
  D3D12DDI_VIDEO_FIELD_TYPE_0020                     FieldType;
  D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020      DeinterlaceMode;
  D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020            StereoFormat;
  DXGI_COLOR_SPACE_TYPE                              ColorSpace;
  D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020           FilterFlags;
  INT                                                FilterLevels[D3D12DDI_VIDEO_PROCESS_MAX_FILTERS];
  D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020         AlphaBlending;
  D3D12DDI_VIDEO_PROCESS_LUMA_KEY_0020               LumaKey;
  D3D12DDI_VIDEO_PROCESS_PALETTE_0020                Palette;
  BOOL                                               EnableAutoProcessing;
} D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020;
````


## -struct-fields




### -field InputStream

The set of references to be able to perform processing. If stereo format is <b>D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_SEPARATE</b>, two sets of input streams must be supplied.  If stereo format is any other mode, the first set of reference must be supplied, and the second should be zero initialized.


### -field Transform

Flip, rotation, scale and destination translation for the video input.  For more information, see the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_process_transform_0020.md">D3D12DDI_VIDEO_PROCESS_TRANSFORM</a> structure. 


### -field Flags

Options for the input stream.  For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_input_stream_flags_0020.md">D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS</a> enumeration.


### -field RateInfo

Frame rate and input and output indexes for frame rate conversion and deinterlacing.  For more information, see the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_process_input_stream_rate_info_0020.md">D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO</a> structure.


### -field FieldType

Frame format as progressive or interlaced for the input stream. 


### -field DeinterlaceMode

The deinterlace mode to use.  For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_deinterlace_flags_0020.md">D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS</a> enumeration.


### -field StereoFormat

Specifies whether the stream is stereo or not. If there is a value of <b>D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_SEPARATE</b>, there are two sets of input textures and references. This is to support a stereo interlaced case.


### -field ColorSpace

The colorspace for the video processor input and reference surfaces as a <a href="https://msdn.microsoft.com/E25C933F-0DB3-4BC4-9755-9361B2B9B9CB">DXGI_COLOR_SPACE_TYPE</a> value.


### -field FilterFlags

The filters to enable, as a bitwise OR of one or more flags from the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_filter_flags_0020.md">D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS</a> enumeration.


### -field FilterLevels

The level to apply for each enabled filter.  If a filter is not enabled or the filter index is reserved, specify zero (0).


### -field AlphaBlending

The planar alpha for an input stream on the video processor.  For more information, see the  <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_process_alpha_blending_0020.md">D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING</a> structure.


### -field LumaKey

The luma key for an input stream on the video processor.  For more information, see the  <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_process_luma_key_0020.md">D3D12DDI_VIDEO_PROCESS_LUMA_KEY</a> structure.


### -field Palette

The palette to use for this stream. If the video processor supports the given palletized formats, it must apply alpha values from color palette entries.


### -field EnableAutoProcessing

Whether to enable automatic processing features on the video processor.


## -see-also

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_process_luma_key_0020.md">D3D12DDI_VIDEO_PROCESS_LUMA_KEY</a>



<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_filter_flags_0020.md">D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS</a>



<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_input_stream_flags_0020.md">D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS</a>



<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_process_alpha_blending_0020.md">D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING</a>



<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_process_input_stream_rate_info_0020.md">D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO</a>



<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_process_transform_0020.md">D3D12DDI_VIDEO_PROCESS_TRANSFORM</a>



<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_deinterlace_flags_0020.md">D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS</a>



<a href="https://msdn.microsoft.com/E25C933F-0DB3-4BC4-9755-9361B2B9B9CB">DXGI_COLOR_SPACE_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020 structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

