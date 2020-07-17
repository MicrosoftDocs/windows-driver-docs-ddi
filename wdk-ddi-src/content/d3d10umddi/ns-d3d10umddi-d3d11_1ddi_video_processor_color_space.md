---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE
title: D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE (d3d10umddi.h)
description: Specifies the color space for video processing.
old-location: display\d3d11_1ddi_video_processor_color_space.htm
ms.assetid: 2878b36e-3850-4af8-aeca-9c5d2da717f9
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE structure"]
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE, D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE, display.d3d11_1ddi_video_processor_color_space
f1_keywords:
 - "d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE"
 - "D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE
---

# D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE structure


## -description


Specifies the color space for video processing.


## -struct-fields




### -field Usage

Specifies whether the output is intended for playback or video processing (such as editing or authoring). The device can optimize the processing based on the type. The default state value is 0 (playback). 



|Value|Meaning|
|--- |--- |
|0|Playback|
|1|Video processing|
 


### -field RGB_Range

Specifies the RGB color range. The default state value is 0 (full range).


|Value|Meaning|
|--- |--- |
|0|Full range (0-255)|
|1|Limited range (16-235)|
 


### -field YCbCr_Matrix

Specifies the YCbCr transfer matrix. The default state value is 0 (BT.601).

|Value|Meaning|
|--- |--- |
|0|ITU-R BT.601|
|1|ITU-R BT.709|


### -field YCbCr_xvYCC

Specifies whether the output uses conventional YCbCr or extended YCbCr (xvYCC). The default state value is zero (conventional YCbCr).

|Value|Meaning|
|--- |--- |
|0|Conventional YCbCr|
|1|Extended YCbCr (xvYCC)|


### -field Nominal_Range

[in] A UINT value that specifies that the luminance range of YUV data is described by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_nominal_range">D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE</a> enumeration. The default state value is zero, which indicates the studio luminance range of 16 to 235, inclusive [16, 235].

When YUV-format data is converted to RGB format, the luminance range specified by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_nominal_range">D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE</a> is applied to the YUV data before the conversion to RGB.

For more information on luminance range, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/yuv-format-ranges">YUV format ranges in Windows 8.1</a>.

Supported starting with Windows 8.1.


### -field Reserved

Reserved for system use. Set to zero.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_nominal_range">D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE</a>
 

 

