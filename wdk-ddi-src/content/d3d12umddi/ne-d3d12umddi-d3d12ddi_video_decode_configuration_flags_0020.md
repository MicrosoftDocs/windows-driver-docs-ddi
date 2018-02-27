---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS_0020
title: D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS_0020
author: windows-driver-content
description: Contains video decode configuration flags.
old-location: display\d3d12ddi_video_decode_configuration_flags.htm
old-project: display
ms.assetid: 33BD5E1F-75F3-44DC-AE83-A22992CAB6B5
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS_0020, D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS_0020 enumeration [Display Devices], D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0020_HEIGHT_ALIGNMENT_MULTIPLE_32_REQUIRED, D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0020_NONE, D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0020_POST_PROCESSING_SUPPORTED, D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0020_REFERENCE_ONLY_ALLOCATIONS_REQUIRED, D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0032_ALLOW_RESOLUTION_CHANGE_ON_NON_KEY_FRAME, d3d12umddi/D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS_0020, d3d12umddi/D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0020_HEIGHT_ALIGNMENT_MULTIPLE_32_REQUIRED, d3d12umddi/D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0020_NONE, d3d12umddi/D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0020_POST_PROCESSING_SUPPORTED, d3d12umddi/D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0020_REFERENCE_ONLY_ALLOCATIONS_REQUIRED, d3d12umddi/D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0032_ALLOW_RESOLUTION_CHANGE_ON_NON_KEY_FRAME, display.d3d12ddi_video_decode_configuration_flags
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
-	D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS_0020
---

# D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS_0020 enumeration


## -description


Contains video decode configuration flags. 


## -syntax


````
typedef enum D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS_0020 { 
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0020_NONE                                      = 0x0,
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0020_HEIGHT_ALIGNMENT_MULTIPLE_32_REQUIRED     = 0x1,
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0020_POST_PROCESSING_SUPPORTED                 = 0x2,
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0020_REFERENCE_ONLY_ALLOCATIONS_REQUIRED       = 0x4,
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0032_ALLOW_RESOLUTION_CHANGE_ON_NON_KEY_FRAME  = 0x8
} D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS_0020;
````


## -enum-fields




### -field D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0020_NONE

Indicates no configuration flags required.


### -field D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0020_HEIGHT_ALIGNMENT_MULTIPLE_32_REQUIRED

Indicates that the height of the output decoded surfaces must be a multiple of 32.


### -field D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0020_POST_PROCESSING_SUPPORTED

Indicates that the driver supports post processing. If this flag is set, the host decoder can set up post-processing by using the conversion flags in <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_decode_conversion_arguments_0021.md">D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS</a>. 


### -field D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0020_REFERENCE_ONLY_ALLOCATIONS_REQUIRED

Indicates that reference resources must be allocated with the <b>D3D12DDI_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY</b> flag in the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_resource_flags_0003.md">D3D12DDI_RESOURCE_FLAGS</a> enumeration.   References textures must be separate from output textures, similar to performing a format conversion or downscale.  This flag must not be set for a value of D3D12DDI_VIDEO_DECODE_TIER_3 or greater. For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_tier_0020.md">D3D12DDI_VIDEO_DECODE_TIER</a> enumeration.


### -field D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAG_0032_ALLOW_RESOLUTION_CHANGE_ON_NON_KEY_FRAME

