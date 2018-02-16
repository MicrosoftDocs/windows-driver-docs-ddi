---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020
title: D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020
author: windows-driver-content
description: Defines the image filter capabilities for a video processor.
old-location: display\d3d12ddi_video_process_filter_flags.htm
old-project: display
ms.assetid: 28662E87-F6A4-42B0-9BF0-49A6C65B245C
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_SATURATION, D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_EDGE_ENHANCEMENT, D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020 enumeration [Display Devices], D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_NOISE_REDUCTION, display.d3d12ddi_video_process_filter_flags, D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_NONE, D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_HUE, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_NOISE_REDUCTION, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_BRIGHTNESS, D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_CONTRAST, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_STEREO_ADJUSTMENT, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_SATURATION, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_CONTRAST, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_HUE, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_EDGE_ENHANCEMENT, D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020, D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_STEREO_ADJUSTMENT, D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_ANAMORPHIC_SCALING, D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_BRIGHTNESS, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_NONE, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_ANAMORPHIC_SCALING, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020
---

# D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020 enumeration


## -description


Defines the image filter capabilities for a video processor. 


## -syntax


````
typedef enum D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020 { 
  D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_NONE                = 0,
  D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_BRIGHTNESS          = 0x1,
  D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_CONTRAST            = 0x2,
  D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_HUE                 = 0x4,
  D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_SATURATION          = 0x8,
  D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_NOISE_REDUCTION     = 0x10,
  D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_EDGE_ENHANCEMENT    = 0x20,
  D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_ANAMORPHIC_SCALING  = 0x40,
  D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_STEREO_ADJUSTMENT   = 0x80
} D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020;
````


## -enum-fields




### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_NONE


### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_BRIGHTNESS

The video processor can adjust the brightness level. 


### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_CONTRAST

The video processor can adjust the contrast level. 


### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_HUE

The video processor can adjust hue. 


### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_SATURATION

The video processor can adjust the saturation level.


### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_NOISE_REDUCTION

The video processor can perform noise reduction. 


### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_EDGE_ENHANCEMENT

The video processor can perform edge enhancement. 


### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_ANAMORPHIC_SCALING

The video processor can perform anamorphic scaling. Anamorphic scaling can be used to stretch 4:3 content to a widescreen 16:9 aspect ratio. 


### -field D3D12DDI_VIDEO_PROCESS_FILTER_FLAG_0020_STEREO_ADJUSTMENT

For stereo 3D video, the video processor can adjust the offset between the left and right views. This allows the user to reduce potential eye strain.


## -remarks



Brightness, hue, contrast, and saturation support are always supported. These capability flags indicate support for the image filters defined by the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_filter_0020.md">D3D12DDI_VIDEO_PROCESS_FILTER</a> enumeration. To apply a particular filter, call the SetInputStreamFilter method.




## -see-also

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_filter_0020.md">D3D12DDI_VIDEO_PROCESS_FILTER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020 enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

