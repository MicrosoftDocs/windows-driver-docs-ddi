---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_PROCESS_FILTER_0020
title: D3D12DDI_VIDEO_PROCESS_FILTER_0020
author: windows-driver-content
description: Contains video process filters.
old-location: display\d3d12ddi_video_process_filter_0020.htm
old-project: display
ms.assetid: A69E2A06-EA08-465C-A1E9-2D7FAB4E2F81
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_PROCESS_FILTER_0020_HUE, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020_EDGE_ENHANCEMENT, D3D12DDI_VIDEO_PROCESS_FILTER_0020_SATURATION, D3D12DDI_VIDEO_PROCESS_FILTER_0020_CONTRAST, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020_BRIGHTNESS, D3D12DDI_VIDEO_PROCESS_FILTER_0020_ANAMORPHIC_SCALING, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020_STEREO_ADJUSTMENT, D3D12DDI_VIDEO_PROCESS_FILTER_0020 enumeration [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020_SATURATION, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020_HUE, D3D12DDI_VIDEO_PROCESS_FILTER_0020_EDGE_ENHANCEMENT, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020_ANAMORPHIC_SCALING, D3D12DDI_VIDEO_PROCESS_FILTER_0020_STEREO_ADJUSTMENT, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020_CONTRAST, display.d3d12ddi_video_process_filter_0020, D3D12DDI_VIDEO_PROCESS_FILTER_0020_NOISE_REDUCTION, D3D12DDI_VIDEO_PROCESS_FILTER_0020, d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_0020_NOISE_REDUCTION, D3D12DDI_VIDEO_PROCESS_FILTER_0020_BRIGHTNESS
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
-	D3D12DDI_VIDEO_PROCESS_FILTER_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_FILTER_0020
---

# D3D12DDI_VIDEO_PROCESS_FILTER_0020 enumeration


## -description


Contains video process filters.


## -syntax


````
typedef enum _D3D12DDI_VIDEO_PROCESS_FILTER_0020 { 
  D3D12DDI_VIDEO_PROCESS_FILTER_0020_BRIGHTNESS          = 0,
  D3D12DDI_VIDEO_PROCESS_FILTER_0020_CONTRAST            = 1,
  D3D12DDI_VIDEO_PROCESS_FILTER_0020_HUE                 = 2,
  D3D12DDI_VIDEO_PROCESS_FILTER_0020_SATURATION          = 3,
  D3D12DDI_VIDEO_PROCESS_FILTER_0020_NOISE_REDUCTION     = 4,
  D3D12DDI_VIDEO_PROCESS_FILTER_0020_EDGE_ENHANCEMENT    = 5,
  D3D12DDI_VIDEO_PROCESS_FILTER_0020_ANAMORPHIC_SCALING  = 6,
  D3D12DDI_VIDEO_PROCESS_FILTER_0020_STEREO_ADJUSTMENT   = 7
} D3D12DDI_VIDEO_PROCESS_FILTER_0020;
````


## -enum-fields




#### - D3D12DDI_VIDEO_PROCESS_FILTER_0020_BRIGHTNESS

The video processor can adjust the brightness level. 


#### - D3D12DDI_VIDEO_PROCESS_FILTER_0020_CONTRAST

The video processor can adjust the contrast level. 


#### - D3D12DDI_VIDEO_PROCESS_FILTER_0020_HUE

The video processor can adjust hue. 


#### - D3D12DDI_VIDEO_PROCESS_FILTER_0020_SATURATION

The video processor can adjust the saturation level.


#### - D3D12DDI_VIDEO_PROCESS_FILTER_0020_NOISE_REDUCTION

The video processor can perform noise reduction. 


#### - D3D12DDI_VIDEO_PROCESS_FILTER_0020_EDGE_ENHANCEMENT

The video processor can perform edge enhancement. 


#### - D3D12DDI_VIDEO_PROCESS_FILTER_0020_ANAMORPHIC_SCALING

The video processor can perform anamorphic scaling. Anamorphic scaling can be used to stretch 4:3 content to a widescreen 16:9 aspect ratio. 


#### - D3D12DDI_VIDEO_PROCESS_FILTER_0020_STEREO_ADJUSTMENT

For stereo 3D video, the video processor can adjust the offset between the left and right views, allowing the user to reduce potential eye strain.

