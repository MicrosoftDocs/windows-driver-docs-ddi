---
UID: NS:d3d12umddi.D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020
title: D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020
description: Specifies output stream parameters for the output to be processed.
old-location: display\d3d12ddiarg_video_process_output_stream_parameters.htm
ms.assetid: F8D7A87D-FFE6-4846-A902-2A686D78F0C1
ms.date: 05/10/2018
ms.keywords: D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020, D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020 structure [Display Devices], d3d12umddi/D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020, display.d3d12ddiarg_video_process_output_stream_parameters
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
req.max-support: Windows 10, version 1709
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
-	D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020
---

# D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020 structure


## -description


Specifies output stream parameters for the output to be processed.


## -struct-fields




### -field OutputStream

The output surfaces for the video process command.  If stereo output is enabled, index 0 contains the left output while index  1 contains the right input.  If stereo output is not enabled, only index 0 is used to specify the output. Index 1 should be a null pointer.


### -field AlphaFillMode

The alpha fill mode for data that the video processor writes to the render target.  For more information, see <a href="https://msdn.microsoft.com/74F07876-5502-4B57-9128-624F6066AF5B">D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE</a> enumeration. 


### -field AlphaFillModeSourceStreamIndex

The zero-based index of an input stream. If the <b>AlphaFillMode</b> member has the value <b>D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_SOURCE_STREAM</b>, this value is used. Otherwise, it is ignored.


### -field BackgroundColor

The background color, which the video processor uses to fill areas of the target rectangle that do not contain a video image. Areas outside the target rectangle are not affected.  The meaning of the values are specified by the <b>ColorSpace</b> member

||YCbCrA|RGBA|
|--- |--- |--- |
|BackgroundColor[0]|Y|R|
|BackgroundColor[1]|Cb|G|
|BackgroundColor[2]|Cr|N|
|BackgroundColor[3]|A|A|


### -field FrameRate

The frame rate of the output video stream, specified as a <a href="https://msdn.microsoft.com/0a878d11-dc90-4cad-bde5-54a135e53a86">DXGI_RATIONAL</a> structure.


### -field EnableStereo

If true, stereo output is enabled. If false, the video processor produces mono video frames.


### -field ColorSpace

The color space for the video processor output surface as a <a href="https://msdn.microsoft.com/E25C933F-0DB3-4BC4-9755-9361B2B9B9CB">DXGI_COLOR_SPACE_TYPE</a> value.


### -field TargetRectangle

The target rectangle, which is the area within the destination surface where the output is drawn. The target rectangle is given in pixel coordinates, relative to the destination surface.


## -see-also




<a href="https://msdn.microsoft.com/74F07876-5502-4B57-9128-624F6066AF5B">D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE</a>



<a href="https://msdn.microsoft.com/E25C933F-0DB3-4BC4-9755-9361B2B9B9CB">DXGI_COLOR_SPACE_TYPE</a>



<a href="https://msdn.microsoft.com/0a878d11-dc90-4cad-bde5-54a135e53a86">DXGI_RATIONAL</a>
 

 

