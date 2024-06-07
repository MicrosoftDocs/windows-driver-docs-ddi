---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CBR1_0096
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CBR1_0096
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CBR1_0096 structure.
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
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CBR1_0096
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CBR1_0096
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CBR1_0096
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CBR1_0096
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CBR1_0096
---

## -description

The **D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CBR_0080** structure contains the extended rate control definition for constant bitrate (CBR) mode.

## -struct-fields

### -field InitialQP

When the [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_ENABLE_INITIAL_QP**](ne-d3d12umddi-d3d12ddi_video_encoder_rate_control_flags_0080.md) flag is set, **InitialQP** can be used by the rate control algorithm.

### -field MinQP

When the [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_ENABLE_QP_RANGE**](ne-d3d12umddi-d3d12ddi_video_encoder_rate_control_flags_0080.md) flag is set, **MinQP** limits the quantization parameter (QP) range of the rate control algorithm.

### -field MaxQP

When the [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_ENABLE_QP_RANGE**](ne-d3d12umddi-d3d12ddi_video_encoder_rate_control_flags_0080.md) flag is set, **MaxQP** limits the QP range of the rate control algorithm.

### -field MaxFrameBitSize

Maximum size for each frame to be encoded, in bits. When [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_ENABLE_MAX_FRAME_SIZE**](ne-d3d12umddi-d3d12ddi_video_encoder_rate_control_flags_0080.md) is set, **MaxFrameBitSize** limits each frame's maximum size in the rate control algorithm.

### -field TargetBitRate

The constant bitrate to be used, in bits per second.

### -field VBVCapacity

When [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_1_ENABLE_VBV_SIZES**](ne-d3d12umddi-d3d12ddi_video_encoder_rate_control_flags_0080.md) is set, **VBVCapacity** specifies the capacity, in bits, of the Video Buffer Verifier (VBV) to be used in the rate control algorithm.

### -field InitialVBVFullness

When [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_1_ENABLE_VBV_SIZES**](ne-d3d12umddi-d3d12ddi_video_encoder_rate_control_flags_0080.md) is set, **InitialVBVFullness** specifies the initial fullness, in bits, of the VBV to be used in the rate control algorithm.

### -field QualityVsSpeed

The quality versus speed trade-off. This value must be in the range [0, D3D12_FEATURE_DATA_VIDEO_ENCODER_SUPPORT1.MaxQualityVsSpeed]. The lower the value, the faster the encode operation.

The settings associated to each of the levels exposed by **QualityVsSpeed** must only refer to hardware/driver implementation optimizations and heuristics that aren't related to specific codec configurations or encoding tools selection, which are already independently exposed in the D3D12 API to the user individually. Please note that other codec configurations and codec encoding tools exposed through this API may also affect quality and speed.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_configuration_params_0080_2.md)

[**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAGS_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_rate_control_flags_0080.md)
