---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032
title: D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032 (d3d12umddi.h)
description: Video decode reference frames.
old-location: display\d3d12ddi-video-decode-reference-frames-0032.htm
ms.assetid: 58a814ab-629e-4528-a349-c469defc0a5a
ms.date: 04/16/2018
keywords: ["D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032 structure"]
ms.keywords: D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032, D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032, display.d3d12ddi-video-decode-reference-frames-0032
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d12umddi.h
api_name:
- D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032
---

# D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032 structure


## -description


Contains the list of reference frames for the current decode operation. Either a Texture Array or an array of textures can be specified.


## -struct-fields




### -field hDrvTexture2Ds

The list of reference textures.


### -field pSubresources

An array of subresource indices for the list of reference textures. NULL indicates a subresource of 0 for each resource.


### -field hDrvVideoDecoderHeaps

Supplies the heap object for a corresponding reference frame. NULL indicates that decoder state allocations for all references is included with the decoder heap in the input stream arguments.
Typically, this parameter is null. VP9 uses this parameter when changing resolution on a non-key frame.



### -field NumTexture2Ds

The number of reference textures.

## -remarks

This structure sets the list of reference frames for the current decode operation. Decode profiles reporting D3D12DDI_VIDEO_DECODE_TIER_1 or D3D12DDI_VIDEO_DECODE_TIER_2 requires the use of a texture array, so the list of hDrvTexture2Ds will always be the same texture and pSubresources is used to index into the texture array.  For D3D12DDI_VIDEO_DECODE_TIER_3, either a Texture Array or an array of textures can be specified.
