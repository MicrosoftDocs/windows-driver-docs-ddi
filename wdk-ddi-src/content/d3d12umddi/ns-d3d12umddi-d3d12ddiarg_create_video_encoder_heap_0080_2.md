---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_ENCODER_HEAP_0080_2
tech.root: display
title: D3D12DDIARG_CREATE_VIDEO_ENCODER_HEAP_0080_2
ms.date: 02/16/2022
targetos: Windows
description: Learn more about D3D12DDIARG_CREATE_VIDEO_ENCODER_HEAP_0080_2
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDIARG_CREATE_VIDEO_ENCODER_HEAP_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_CREATE_VIDEO_ENCODER_HEAP_0080_2
f1_keywords:
 - D3D12DDIARG_CREATE_VIDEO_ENCODER_HEAP_0080_2
 - d3d12umddi/D3D12DDIARG_CREATE_VIDEO_ENCODER_HEAP_0080_2
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDIARG_CREATE_VIDEO_ENCODER_HEAP_0080_2
---

## -description

The **D3D12DDIARG_CREATE_VIDEO_ENCODER_HEAP_0080_2** structure specifies video encoder heap parameters.

## -struct-fields

### -field NodeMask

For a single GPU operation, set **NodeMask** to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only one bit can be set.

### -field Flags

A [**D3D12DDI_VIDEO_ENCODER_HEAP_FLAGS_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_heap_flags_0080.md) value that specifies the video encoder heap creation flags.

### -field EncodeCodec

A [**D3D12DDI_VIDEO_ENCODER_CODEC_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_0080.md) value that identifies the codec of the associated encoder object.

### -field EncodeProfile

A [**D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_profile_desc_0080_2.md) structure that identifies the codec's profile.

### -field EncodeLevel

A [**D3D12DDI_VIDEO_ENCODER_LEVEL_SETTING_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_level_setting_0080_2.md) structure that indicates the level for the specified codec and the profile in the associated encoder object.

### -field ResolutionsListCount

Number of lists that **pResolutionList** points to.

### -field pResolutionList

Pointer to a list of [**D3D12DDI_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC_0080**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_resolution_desc_0080.md) structures that contain picture resolutions requested to be supported.

## -remarks

If support for resolution dynamic reconfiguration is not supported, only one resolution is passed to denote the desired target resolution.

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDICAPS_VIDEO_ENCODER_HEAP_SIZE_DATA_0080_2**](ns-d3d12umddi-d3d12ddicaps_video_encoder_heap_size_data_0080_2.md)

[**PFND3D12DDI_CALCPRIVATEVIDEOENCODERHEAPSIZE_0080_2**](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideoencoderheapsize_0080_2.md)

[**PFND3D12DDI_CREATEVIDEOENCODERHEAP_0080_2**](nc-d3d12umddi-pfnd3d12ddi_createvideoencoderheap_0080_2.md)
