---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032
title: D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032
author: windows-driver-content
description: Describes output stream properties for the video processor.
old-location: display\d3d12ddi_video_process_output_stream_desc_0032.htm
old-project: display
ms.assetid: 5A995E97-4522-44CD-89C3-521724142D7F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032, D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032, display.d3d12ddi_video_process_output_stream_desc_0032
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032
---

# D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032 structure


## -description


Describes output stream properties for the video processor.


## -syntax


````
typedef struct _D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032 {
  DXGI_FORMAT                                 Format;
  DXGI_COLOR_SPACE_TYPE                       ColorSpace;
  D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020 AlphaFillMode;
  UINT                                        AlphaFillModeSourceStreamIndex;
  FLOAT                                       BackgroundColor[4];
  DXGI_RATIONAL                               FrameRate;
  BOOL                                        EnableStereo;
} D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032;
````


## -struct-fields




### -field Format

The DXGI format of the output texture.


### -field ColorSpace

A DXGI_COLOR_SPACE_TYPE value that specifies the colorspace for the video processor output surface.


### -field AlphaFillMode

The alpha fill mode for data that the video processor writes to the render target.  See D3D12DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE.


### -field AlphaFillModeSourceStreamIndex

The zero-based index of an input stream. This parameter is used if AlphaFillMode is D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_SOURCE_STREAM. Otherwise, the parameter is ignored.


### -field BackgroundColor

 


### -field FrameRate

The frame rate of the output video stream, specified as a DXGI_RATIONAL structure.


### -field EnableStereo

If TRUE, stereo output is enabled. Otherwise, the video processor produces mono video frames.


#### - BackgroundColor[4]

The video processor uses the background color to fill areas of the target rectangle that do not contain a video image. Areas outside the target rectangle are not affected.  The meaning of the values is specified by the ColorSpace parameter.

<table>
<tr>
<th></th>
<th>YCbCrA</th>
<th>RGBA</th>
</tr>
<tr>
<td>BackgroundColor[0]</td>
<td>Y</td>
<td>R</td>
</tr>
<tr>
<td>BackgroundColor[1]</td>
<td>Cb</td>
<td>G</td>
</tr>
<tr>
<td>BackgroundColor[2]</td>
<td>Cr</td>
<td>B</td>
</tr>
<tr>
<td>BackgroundColor[3]</td>
<td>A</td>
<td>A</td>
</tr>
</table>
 

