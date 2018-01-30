---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE
title: D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE
author: windows-driver-content
description: Specifies the color space for video processing.
old-location: display\d3d11_1ddi_video_processor_color_space.htm
old-project: display
ms.assetid: 2878b36e-3850-4af8-aeca-9c5d2da717f9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d11_1ddi_video_processor_color_space, D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE, D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE
---

# D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE structure


## -description


Specifies the color space for video processing.


## -syntax


````
typedef struct D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE {
  UINT Usage  :1;
  UINT RGB_Range  :1;
  UINT YCbCr_Matrix  :1;
  UINT YCbCr_xvYCC  :1;
  UINT Nominal_Range  :2;
  UINT Reserved  :26;
} D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE;
````


## -struct-fields




### -field Usage

Specifies whether the output is intended for playback or video processing (such as editing or authoring). The device can optimize the processing based on the type. The default state value is 0 (playback). 


<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
Playback

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>1</dt>
</dl>
</td>
<td width="60%">
Video processing

</td>
</tr>
</table> 


### -field RGB_Range

Specifies the RGB color range. The default state value is 0 (full range).


<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
Full range (0-255)

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>1</dt>
</dl>
</td>
<td width="60%">
Limited range (16-235)

</td>
</tr>
</table> 


### -field YCbCr_Matrix

Specifies the YCbCr transfer matrix. The default state value is 0 (BT.601).


<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
ITU-R BT.601

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>1</dt>
</dl>
</td>
<td width="60%">
ITU-R BT.709

</td>
</tr>
</table> 


### -field YCbCr_xvYCC

Specifies whether the output uses conventional YCbCr or extended YCbCr (xvYCC). The default state value is zero (conventional YCbCr).


<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
Conventional YCbCr

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>1</dt>
</dl>
</td>
<td width="60%">
Extended YCbCr (xvYCC)

</td>
</tr>
</table> 


### -field Nominal_Range

[in] A UINT value that specifies that the luminance range of YUV data is described by the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_nominal_range.md">D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE</a> enumeration. The default state value is zero, which indicates the studio luminance range of 16 to 235, inclusive [16, 235].

When YUV-format data is converted to RGB format, the luminance range specified by <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_nominal_range.md">D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE</a> is applied to the YUV data before the conversion to RGB.

For more information on luminance range, see <a href="https://msdn.microsoft.com/D76FFB8C-CA42-446E-826F-52982B1849E5">YUV format ranges in Windows 8.1</a>.

Supported starting with Windows 8.1.


### -field Reserved

Reserved for system use. Set to zero.


## -see-also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_nominal_range.md">D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

