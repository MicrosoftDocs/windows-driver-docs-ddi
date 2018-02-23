---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022
title: D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022
author: windows-driver-content
description: Contains the options for video scale support.
old-location: display\d3d12ddi_video_scale_support_flags.htm
old-project: display
ms.assetid: A0E1AA43-FE1A-4754-B8E6-BFE87CA810E2
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0022_POW2_ONLY, d3d12umddi/D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022, D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0022_EVEN_DIMENSIONS_ONLY, D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022 enumeration [Display Devices], D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0020_NONE, d3d12umddi/D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0022_POW2_ONLY, d3d12umddi/D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0020_NONE, d3d12umddi/D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0022_EVEN_DIMENSIONS_ONLY, display.d3d12ddi_video_scale_support_flags, D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022
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
-	D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022
---

# D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022 enumeration


## -description


Contains the options for video scale support.


## -syntax


````
typedef enum D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022 { 
  D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0020_NONE                  = 0x0,
  D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0022_POW2_ONLY             = 0x1,
  D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0022_EVEN_DIMENSIONS_ONLY  = 0x2
} D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022;
````


## -enum-fields




### -field D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0022_NONE


### -field D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0022_POW2_ONLY

The scaler supports only output sizes at a pow2 scale factors within the range.  The x and y scale factors must be the same for both dimensions when this flag is set.


### -field D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0022_EVEN_DIMENSIONS_ONLY

The scaler supports only output sizes that have even output dimensions.


#### - D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0020_NONE

All possible output size width/height combinations that exist between the maximum size and minimum size for the extent, inclusive, are supported.  

