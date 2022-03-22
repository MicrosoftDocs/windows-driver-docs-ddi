---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_QVBR_0080_2
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_QVBR_0080_2
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_QVBR_0080_2 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_QVBR_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_QVBR_0080_2
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_QVBR_0080_2
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_QVBR_0080_2
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_QVBR_0080_2
---

## -description

The **D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_QVBR_0080_2** structure contains the rate control definition for constant quality target with constrained bitrate.

## -struct-fields

### -field InitialQP

When the [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_ENABLE_INITIAL_QP**](ne-d3d12umddi-d3d12ddi_video_encoder_rate_control_flags_0080.md) flag is set, **InitialQP** can be used by the rate control algorithm.

### -field MinQP

When the [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_ENABLE_QP_RANGE**](ne-d3d12umddi-d3d12ddi_video_encoder_rate_control_flags_0080.md) flag is set, **MinQP** limits the quantization parameter (QP) range of the rate control algorithm.

### -field MaxQP

When the [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_ENABLE_QP_RANGE**](ne-d3d12umddi-d3d12ddi_video_encoder_rate_control_flags_0080.md) flag is set, **MaxQP** limits the QP range of the rate control algorithm.

### -field MaxFrameBitSize

Maximum size for each frame to be encoded, in bits. When [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_ENABLE_MAX_FRAME_SIZE**](ne-d3d12umddi-d3d12ddi_video_encoder_rate_control_flags_0080.md) is set, **MaxFrameBitSize** limits each frame's maximum size in the rate control algorithm.

### -field TargetAvgBitRate

Average bitrate to be used, in bits per second.

### -field PeakBitRate

Maximum bitrate that can be reached, in bits per second.

### -field ConstantQualityTarget

Indicates the quality level. Values are codec-specific as each standard defines the range for this argument (for example, H.264 / HEVC 0-51, et cetera).

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_configuration_params_0080_2.md)

[**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAGS_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_rate_control_flags_0080.md)
