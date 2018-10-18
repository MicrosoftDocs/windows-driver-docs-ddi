---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_SIZE_RANGE_0032
title: D3D12DDI_VIDEO_SIZE_RANGE_0032
author: windows-driver-content
description: Video size range.
old-location: display\d3d12ddi-video-size-range-0032.htm
ms.assetid: a4781fea-4efc-442d-8503-12be17afa9b1
ms.date: 4/16/2018
ms.keywords: D3D12DDI_VIDEO_SIZE_RANGE_0032, D3D12DDI_VIDEO_SIZE_RANGE_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_SIZE_RANGE_0032, display.d3d12ddi-video-size-range-0032
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
-	D3D12DDI_VIDEO_SIZE_RANGE_0032
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_SIZE_RANGE_0032
---

# D3D12DDI_VIDEO_SIZE_RANGE_0032 structure


## -description


Describes a supported range of output sizes for a scaler.


## -struct-fields




### -field MaxWidth

The largest output Width that can be scaled to. The largest value allowed is D3D12_REQ_TEXTURE2D_U_OR_V_DIMENSION (16384).


### -field MaxHeight

The largest output Height that can be scaled to. The largest value allowed is D3D12_REQ_TEXTURE2D_U_OR_V_DIMENSION (16384).


### -field MinWidth

The smallest output Width that can be scaled to. The smallest allowed value is 1.


### -field MinHeight

The smallest output Height that can be scaled to. The smallest allowed value is 1.


## -remarks

By default, the supported range indicates all possible output size combinations that exist between the Max size and Min size for the extent, ScaleSupportFlags may add additional caveats.

When scaling is not supported, the Min and Max sizes should both be set to the input size and no flags specified.


## -see-also

[D3D12DDI_VIDEO_SCALE_SUPPORT_0032 structure](ns-d3d12umddi-d3d12ddi_video_scale_support_0032.md)
