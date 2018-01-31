---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS
author: windows-driver-content
description: Defines stereo 3-D capabilities for a Microsoft Direct3D 11 video processor.
old-location: display\d3d11_1ddi_video_processor_stereo_caps.htm
old-project: display
ms.assetid: 02b096be-0f9e-4ea3-a13f-1c6ad7c802c9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_CHECKERBOARD, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS enumeration [Display Devices], D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_CHECKERBOARD, display.d3d11_1ddi_video_processor_stereo_caps, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_MONO_OFFSET, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_ROW_INTERLEAVED, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_FLIP_MODE, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_COLUMN_INTERLEAVED, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_FLIP_MODE, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_MONO_OFFSET, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_ROW_INTERLEAVED, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_COLUMN_INTERLEAVED
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
-	D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS
---

# D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS enumeration


## -description


Defines stereo 3-D capabilities for a Microsoft Direct3D 11 video processor.


## -syntax


````
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS { 
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_MONO_OFFSET         = 0x1,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_ROW_INTERLEAVED     = 0x2,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_COLUMN_INTERLEAVED  = 0x4,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_CHECKERBOARD        = 0x8,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_FLIP_MODE           = 0x10
} D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS;
````


## -enum-fields




#### - D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_MONO_OFFSET

The video processor supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET</b> format defined in the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_format.md">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT</a> enumeration.


#### - D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_ROW_INTERLEAVED

The video processor supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_ROW_INTERLEAVED</b> format.


#### - D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_COLUMN_INTERLEAVED

The video processor supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_COLUMN_INTERLEAVED</b> 
 format.


#### - D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_CHECKERBOARD

The video processor supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_CHECKERBOARD</b> 
format.


#### - D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_FLIP_MODE

The video processor can flip one or both views. For more information, see <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_flip_mode.md">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE</a>.


## -see-also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_format.md">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT</a>

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_flip_mode.md">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

