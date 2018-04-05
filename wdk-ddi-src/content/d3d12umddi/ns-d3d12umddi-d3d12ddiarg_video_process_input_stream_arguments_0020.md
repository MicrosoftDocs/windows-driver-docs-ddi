---
UID: NS:d3d12umddi.D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020
title: D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020
author: windows-driver-content
description: Specifies input stream parameters for an input stream passed to the pfnProcessFrame callback function.
old-location: display\d3d12ddiarg_video_process_input_stream_parameters.htm
old-project: display
ms.assetid: 2488E73E-CF47-4852-8090-BC063DCC4EA4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020, D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020 structure [Display Devices], d3d12umddi/D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020, display.d3d12ddiarg_video_process_input_stream_parameters
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020
product:
- Windows
targetos: Windows
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

Options for the input stream.  For more information, see the <a href="https://msdn.microsoft.com/6BF1C31E-45F8-4921-87A2-53331530EAC4">D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS</a> enumeration.


### -field RateInfo

Frame rate and input and output indexes for frame rate conversion and deinterlacing.  For more information, see the <a href="https://msdn.microsoft.com/3F92B206-BA05-4ECC-854B-8D1EA9D7FD19">D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO</a> structure.


### -field FieldType

Frame format as progressive or interlaced for the input stream. 


### -field DeinterlaceMode

The deinterlace mode to use.  For more information, see the <a href="https://msdn.microsoft.com/7E34CCE5-A771-4EBE-A09B-79424405BFF3">D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS</a> enumeration.


### -field StereoFormat

Specifies whether the stream is stereo or not. If there is a value of <b>D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_SEPARATE</b>, there are two sets of input textures and references. This is to support a stereo interlaced case.


### -field ColorSpace

The colorspace for the video processor input and reference surfaces as a <a href="https://msdn.microsoft.com/E25C933F-0DB3-4BC4-9755-9361B2B9B9CB">DXGI_COLOR_SPACE_TYPE</a> value.


### -field FilterFlags

The filters to enable, as a bitwise OR of one or more flags from the <a href="https://msdn.microsoft.com/28662E87-F6A4-42B0-9BF0-49A6C65B245C">D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS</a> enumeration.


### -field FilterLevels

The level to apply for each enabled filter.  If a filter is not enabled or the filter index is reserved, specify zero (0).


### -field AlphaBlending

The planar alpha for an input stream on the video processor.  For more information, see the  <a href="https://msdn.microsoft.com/58E7A600-1CA9-40F8-8F37-CA7A0834B3F4">D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING</a> structure.


### -field LumaKey

The luma key for an input stream on the video processor.  For more information, see the  <a href="https://msdn.microsoft.com/79D8C170-A562-45F4-834B-58D8F7490C36">D3D12DDI_VIDEO_PROCESS_LUMA_KEY</a> structure.


### -field Palette

The palette to use for this stream. If the video processor supports the given palletized formats, it must apply alpha values from color palette entries.


### -field EnableAutoProcessing

Whether to enable automatic processing features on the video processor.


## -see-also




<a href="https://msdn.microsoft.com/58E7A600-1CA9-40F8-8F37-CA7A0834B3F4">D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING</a>



<a href="https://msdn.microsoft.com/7E34CCE5-A771-4EBE-A09B-79424405BFF3">D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS</a>



<a href="https://msdn.microsoft.com/28662E87-F6A4-42B0-9BF0-49A6C65B245C">D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS</a>



<a href="https://msdn.microsoft.com/6BF1C31E-45F8-4921-87A2-53331530EAC4">D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS</a>



<a href="https://msdn.microsoft.com/3F92B206-BA05-4ECC-854B-8D1EA9D7FD19">D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO</a>



<a href="https://msdn.microsoft.com/79D8C170-A562-45F4-834B-58D8F7490C36">D3D12DDI_VIDEO_PROCESS_LUMA_KEY</a>



<a href="https://msdn.microsoft.com/E463BD7F-F89C-4D82-ABCA-4AF48EC21655">D3D12DDI_VIDEO_PROCESS_TRANSFORM</a>



<a href="https://msdn.microsoft.com/E25C933F-0DB3-4BC4-9755-9361B2B9B9CB">DXGI_COLOR_SPACE_TYPE</a>
 

 

