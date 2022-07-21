---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_ENCODER_0082_0
tech.root: display
title: D3D12DDIARG_CREATE_VIDEO_ENCODER_0082_0 structure (d3d12umddi.h)
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDIARG_CREATE_VIDEO_ENCODER_0082_0 structure.
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
req.typenames: D3D12DDIARG_CREATE_VIDEO_ENCODER_0082_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_CREATE_VIDEO_ENCODER_0082_0
f1_keywords:
 - D3D12DDIARG_CREATE_VIDEO_ENCODER_0082_0
 - d3d12umddi/D3D12DDIARG_CREATE_VIDEO_ENCODER_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDIARG_CREATE_VIDEO_ENCODER_0082_0** structure contains the encoder creation parameters for the [**PFND3D12DDI_CALCPRIVATEVIDEOENCODERSIZE_0082_0**](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideoencodersize_0082_0.md) and [**PFND3D12DDI_CREATEVIDEOENCODER_0082_0**](nc-d3d12umddi-pfnd3d12ddi_createvideoencoder_0082_0.md) callback functions.

## -struct-fields

### -field NodeMask

For a single GPU operation, set **NodeMask** to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only one bit can be set.

### -field Flags

A [**D3D12DDI_VIDEO_ENCODER_FLAGS_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_flags_0080.md) value that specifies the encoder creation flags.

### -field EncodeCodec

A [**D3D12DDI_VIDEO_ENCODER_CODEC_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_0080.md) value that identifies the codec type.

### -field EncodeProfile

A [**D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_profile_desc_0080_2.md) structure that identifies the codec's profile.

### -field InputFormat

A [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format) structure that indicates the format of the source stream.

### -field CodecConfiguration

A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_0082_0.md) structure that indicates the sequence-level codec-specific parameters.

### -field MaxMotionEstimationPrecision

A [**D3D12DDI_VIDEO_ENCODER_MOTION_ESTIMATION_PRECISION_MODE_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_motion_estimation_precision_mode_0080.md) value that identifies the motion estimation precision mode.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**PFND3D12DDI_CALCPRIVATEVIDEOENCODERSIZE_0082_0**](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideoencodersize_0082_0.md)

[**PFND3D12DDI_CREATEVIDEOENCODER_0082_0**](nc-d3d12umddi-pfnd3d12ddi_createvideoencoder_0082_0.md)
