---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_DECODE_TIER_0020
title: D3D12DDI_VIDEO_DECODE_TIER_0020
author: windows-driver-content
description: Specifies the video decode tier.
old-location: display\d3d12ddi_video_decode_tier.htm
old-project: display
ms.assetid: CC4B83A3-1F57-493F-840F-F0F799B631E6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_TIER_0020, D3D12DDI_VIDEO_DECODE_TIER_0020 enumeration [Display Devices], D3D12DDI_VIDEO_DECODE_TIER_0020_1, D3D12DDI_VIDEO_DECODE_TIER_0020_2, D3D12DDI_VIDEO_DECODE_TIER_0020_3, D3D12DDI_VIDEO_DECODE_TIER_0020_NOT_SUPPORTED, d3d12umddi/D3D12DDI_VIDEO_DECODE_TIER_0020, d3d12umddi/D3D12DDI_VIDEO_DECODE_TIER_0020_1, d3d12umddi/D3D12DDI_VIDEO_DECODE_TIER_0020_2, d3d12umddi/D3D12DDI_VIDEO_DECODE_TIER_0020_3, d3d12umddi/D3D12DDI_VIDEO_DECODE_TIER_0020_NOT_SUPPORTED, display.d3d12ddi_video_decode_tier
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_DECODE_TIER_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_TIER_0020
---

# D3D12DDI_VIDEO_DECODE_TIER_0020 enumeration


## -description


Specifies the video decode tier. Decode video tiers consolidate a set of hardware capabilities. The higher the tier, the more capable the hardware.


## -syntax


````
typedef enum D3D12DDI_VIDEO_DECODE_TIER_0020 {
  D3D12DDI_VIDEO_DECODE_TIER_0020_NOT_SUPPORTED  = 0,
  D3D12DDI_VIDEO_DECODE_TIER_0020_1              = 1,
  D3D12DDI_VIDEO_DECODE_TIER_0020_2              = 2,
  D3D12DDI_VIDEO_DECODE_TIER_0020_3              = 3
} D3D12DDI_VIDEO_DECODE_TIER_0020;
````


## -enum-fields




### -field D3D12DDI_VIDEO_DECODE_TIER_0020_NOT_SUPPORTED

The decode profile is not supported.


### -field D3D12DDI_VIDEO_DECODE_TIER_0020_1

Video decode tier 1. In decode tier 1, hardware requires decode output textures and reference textures for decoding a stream to be allocated such that they are “close” to one another.


### -field D3D12DDI_VIDEO_DECODE_TIER_0020_2

Video decode tier 2. Decode tier 2 allows the caller to allocate reference and output textures as separate 2D texture resources.  The application is no longer required to allocate texture arrays, but this must be supported.


### -field D3D12DDI_VIDEO_DECODE_TIER_0020_3

Video decode tier 3. This tier is not currently enabled in the runtime or defined.

## -remarks

The following table shows the different capabilities of each tier:

| | Tier 1 | Tier 2 | Tier 3 |
| -- | -- | -- | -- |
| Supports individually allocated reference frames and output. | No | Yes | Required |
| Supports references and allocated as a texture array. | Required | Required | Required |
| May optionally require the REFERENCE_ONLY resource flag. Note that all tiers are required to work with flag present, even when its not required. | Optional | Optional | No |
| Support for references allocated with REFERENCE_ONLY, even when caps do not require it. | Required | Required | Required |
| Supports Tiled/Sparse resources for references, input and output. | No | No | Required |
|  | Required | Required | Required |

Other required capabilities for all tiers include:

* Compressed bit stream input buffers may be allocated as L0 (main system memory) or L1 (for dGPU, video memory).
* Requires compressed bitstream data for slices to be located in a single buffer allocation with no gaps between slices.
* Offset to first slice in the  compressed input buffer must be 256 byte aligned.
* Drivers must not perform additional copies of the compressed bitstream data.
