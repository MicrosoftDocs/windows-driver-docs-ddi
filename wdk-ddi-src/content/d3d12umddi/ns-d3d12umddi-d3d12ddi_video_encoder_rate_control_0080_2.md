---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_0080_2
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_0080_2
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_0080_2 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_0080_2
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_0080_2
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_0080_2
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_0080_2
---

## -description

The **D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_0080_2** structure specifies the rate control configuration.

## -struct-fields

### -field Mode

A [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_rate_control_mode_0080.md) value that specifies the rate control mode.

### -field Flags

A [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAGS_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_rate_control_flags_0080.md) value that specifies the flags for rate control.

### -field ConfigParams

A [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_configuration_params_0080_2.md) structure whose members point to specific configuration structures based on **Mode**. For absolute quantization parameter (QP) matrix mode, the configuration arguments are provided on a per [**EncodeFrame**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md) basis.

If **Mode** is **D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_0080_ABSOLUTE_QP_MAP**, the QP values in **pRateControlQPMap** are used as absolute QP values.

For the other rate control modes, the QP values in **pRateControlQPMap** are interpreted as a delta QP map to be used for the current [frame encode operation](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md). The values provided in the map are incremented/decremented on top of the QP values decided by the rate control algorithm or the baseline QP constant set in CQP mode.

### -field TargetFrameRate

A [**DXGI_RATIONAL**](/windows/win32/api/dxgicommon/ns-dxgicommon-dxgi_rational) structure that indicates the target frame rate for the encoded stream. This value is a hint for the rate control budgeting algorithm.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_control_desc_0082_0.md)

[**PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md)
