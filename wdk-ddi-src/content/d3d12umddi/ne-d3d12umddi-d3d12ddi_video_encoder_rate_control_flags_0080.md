---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAGS_0080
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAGS_0080
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAGS_0080 enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAGS_0080
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAGS_0080
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAGS_0080
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAGS_0080
---

## -description

The **D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAGS_0080** enumeration specifies the flags for [rate control](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_0080_2.md).

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_NONE:0x0

No rate control flags.

### -field D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_ENABLE_DELTA_QP:0x1

If the selected rate control mode is [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_ABSOLUTE_QP_MAP**](ne-d3d12umddi-d3d12ddi_video_encoder_rate_control_mode_0080.md), this flag has no effect since the QP values in **pRateControlQPMap** field are used as absolute QP values.

For the other rate control modes, this flag enables **pRateControlQPMap** to be interpreted as a delta QP map to be used for the current [frame encode operation](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md). The values provided in the map are incremented/decremented on top of the QP values decided by the rate control algorithm or the baseline QP constant set in CQP mode.

Using delta QP adjustment along with some active rate control modes might violate bitrate constraints as it explicitly alters the QP values that were selected by the rate control budgeting algorithm.

### -field D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_ENABLE_FRAME_ANALYSIS:0x2

If support is indicated in [**D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_support_flags_0083_0.md), this flag enables the rate control algorithm to optimize bitrate usage by selecting QP values based on statistics collected by doing frame analysis on a first pass.

### -field D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_ENABLE_QP_RANGE:0x4

When set, use the **MinQp** and **MaxQp** values as a range for the rate control algorithm.

### -field D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_ENABLE_INITIAL_QP:0x8

When set, use the **InitialQP** values as a range for the rate control algorithm.

### -field D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_ENABLE_MAX_FRAME_SIZE:0x10

When [**D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_RATE_CONTROL_MAX_FRAME_SIZE_AVAILABLE**](ne-d3d12umddi-d3d12ddi_video_encoder_support_flags_0083_0.md) is supported, the rate control algorithm should limit the maximum size per frame to the specified parameter in the rate control configuration.

### -field D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0080_1_ENABLE_VBV_SIZES:0x20

When set, enable the usage of **VBVCapacity** and **InitialVBVFullness**.

### -field D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0096_ENABLE_EXTENSION1_SUPPORT:0x40

Requires [**D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_RATE_CONTROL_EXTENSION1_SUPPORT**](ne-d3d12umddi-d3d12ddi_video_encoder_support_flags_0083_0.md) to be set. See Remarks.

### -field D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0096_ENABLE_QUALITY_VS_SPEED:0x80

Requires **D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_RATE_CONTROL_EXTENSION1_SUPPORT** and **D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_RATE_CONTROL_QUALITY_VS_SPEED_AVAILABLE**. When enabled, indicates the use of **QualityVsSpeed** in the rate control structure.

## -remarks

When **D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAG_0096_ENABLE_EXTENSION1_SUPPORT** is enabled, this indicates that the rate control structures extended for AV1 encoding will be used in [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS.pConfiguration_*Xxx***](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_configuration_params_0080_2.md), as per the following table.

| Rate control mode when flag is enabled | D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS type | D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS DataSize |
| -------------------------------------- | ------------------------------------------------------------- | ----------------------------------------------------------------- |
| D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_ABSOLUTE_QP_MAP | D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_ABSOLUTE_QP_MAP | sizeof(D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_ABSOLUTE_QP_MAP) |
| D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_CQP             | D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CQP1            | sizeof(D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CQP1) |
| D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_CBR             | D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CBR1            | sizeof(D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CBR1) |
| D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_VBR             | D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_VBR1            | sizeof(D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_VBR1) |
| D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_QVBR            | D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_QVBR1           | sizeof(D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_QVBR1) |

Otherwise, the legacy structures will be used when disabled, as per the following table.

| Rate control mode when flag is disabled | D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS type  | D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS DataSize |
| --------------------------------------- | -------------------------------------------------------------- | ----------------------------------------------------------------- |
| D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_ABSOLUTE_QP_MAP | NULL | 0 |
| D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_CQP | D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CQP | sizeof(D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CQP) |
| D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_CBR | D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CBR | sizeof(D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CBR) |
| D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_VBR | D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_VBR | sizeof(D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_VBR) |
| D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_QVBR | D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_QVBR | sizeof(D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_QVBR) |

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_0080_2.md)

[**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CBR_0080**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_cbr_0080.md)

[**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_QVBR_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_qvbr_0080_2.md)

[**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_VBR_0080**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_vbr_0080.md)

[**D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0083_0**](ne-d3d12umddi-d3d12ddi_video_encoder_support_flags_0083_0.md)

[**PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md)
