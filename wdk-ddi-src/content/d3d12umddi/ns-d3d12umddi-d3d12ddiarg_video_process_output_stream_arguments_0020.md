---
UID: NS:d3d12umddi.D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020
title: D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020
author: windows-driver-content
description: Specifies output stream parameters for the output to be processed.
old-location: display\d3d12ddiarg_video_process_output_stream_parameters.htm
old-project: display
ms.assetid: F8D7A87D-FFE6-4846-A902-2A686D78F0C1
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 0, 1, 2, 3, A, C, D, D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020, D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020 structure [Display Devices], E, G, I, M, N, O, P, R, S, T, U, V, _, d3d12umddi/D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020, display.d3d12ddiarg_video_process_output_stream_parameters"
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
-	D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020
---

# D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020 structure


## -description


Specifies output stream parameters for the output to be processed.


## -syntax


````
typedef struct D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020 {
  D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020   OutputStream[2];
  D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020 AlphaFillMode;
  UINT                                        AlphaFillModeSourceStreamIndex;
  FLOAT                                       BackgroundColor[4];
  DXGI_RATIONAL                               FrameRate;
  BOOL                                        EnableStereo;
  DXGI_COLOR_SPACE_TYPE                       ColorSpace;
  D3D12DDI_RECT                               TargetRectangle;
} D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020;
````


## -struct-fields




### -field OutputStream

The output surfaces for the video process command.  If stereo output is enabled, index 0 contains the left output while index  1 contains the right input.  If stereo output is not enabled, only index 0 is used to specify the output. Index 1 should be a null pointer.


### -field AlphaFillMode

The alpha fill mode for data that the video processor writes to the render target.  For more information, see <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_alpha_fill_mode_0020.md">D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE</a> enumeration. 


### -field AlphaFillModeSourceStreamIndex

The zero-based index of an input stream. If the <b>AlphaFillMode</b> member has the value <b>D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_SOURCE_STREAM</b>, this value is used. Otherwise, it is ignored.


### -field BackgroundColor

The background color, which the video processor uses to fill areas of the target rectangle that do not contain a video image. Areas outside the target rectangle are not affected.  The meaning of the values are specified by the <b>ColorSpace</b> member

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
<td>N</td>
</tr>
<tr>
<td>BackgroundColor[3]</td>
<td>A</td>
<td>A</td>
</tr>
</table>
 


### -field FrameRate

The frame rate of the output video stream, specified as a <a href="https://msdn.microsoft.com/0a878d11-dc90-4cad-bde5-54a135e53a86">DXGI_RATIONAL</a> structure.


### -field EnableStereo

If true, stereo output is enabled. If false, the video processor produces mono video frames.


### -field ColorSpace

The colorspace for the video processor output surface as a <a href="https://msdn.microsoft.com/E25C933F-0DB3-4BC4-9755-9361B2B9B9CB">DXGI_COLOR_SPACE_TYPE</a> value.


### -field TargetRectangle

The target rectangle, which is the area within the destination surface where the output is drawn. The target rectangle is given in pixel coordinates, relative to the destination surface.


## -see-also

<a href="https://msdn.microsoft.com/E25C933F-0DB3-4BC4-9755-9361B2B9B9CB">DXGI_COLOR_SPACE_TYPE</a>



<a href="https://msdn.microsoft.com/0a878d11-dc90-4cad-bde5-54a135e53a86">DXGI_RATIONAL</a>



<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_alpha_fill_mode_0020.md">D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020 structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

