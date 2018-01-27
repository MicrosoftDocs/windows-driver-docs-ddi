---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS
author: windows-driver-content
description: Defines capabilities related to input formats for a Microsoft Direct3D 11 video processor.
old-location: display\d3d11_1ddi_video_processor_format_caps.htm
old-project: display
ms.assetid: b0f36d4c-cf95-4d85-a2c8-267df618e0aa
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_RGB_LUMA_KEY, D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_PALETTE_INTERLACED, D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS enumeration [Display Devices], display.d3d11_1ddi_video_processor_format_caps, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_RGB_INTERLACED, D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_PALETTE_INTERLACED, D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_RGB_LUMA_KEY, D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_RGB_INTERLACED, D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_RGB_PROCAMP, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_RGB_PROCAMP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS
---

# D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS enumeration


## -description


Defines capabilities related to input formats for a Microsoft Direct3D 11 video processor.


## -syntax


````
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS { 
  D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_RGB_INTERLACED      = 0x1,
  D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_RGB_PROCAMP         = 0x2,
  D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_RGB_LUMA_KEY        = 0x4,
  D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_PALETTE_INTERLACED  = 0x8
} D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS;
````


## -enum-fields




### -field D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_RGB_INTERLACED

The video processor can deinterlace an input stream that contains interlaced RGB video.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_RGB_PROCAMP

The video processor can perform color adjustment on RGB video.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_RGB_LUMA_KEY

The video processor can perform luma keying on RGB video.


### -field D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_PALETTE_INTERLACED

The video processor can deinterlace input streams with palettized color formats.


## -remarks


These flags define video processing capabilities that usually are not needed, and that video devices are therefore not required to support.

The first three flags relate to RGB support for functions that are normally applied to YCbCr video: deinterlacing, color adjustment, and luma keying. A device that supports these functions for YCbCr is not required to support them for RGB input. Supporting RGB input for these functions is an additional capability, reflected by these constants. Note that the driver might convert the input to another color space, perform the indicated function, and then convert the result back to RGB

Similarly, a device that supports deinterlacing is not required to support deinterlacing of palettized formats. This capability is indicated by the <b>D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS_PALETTE_INTERLACED</b>  enumeration value.


