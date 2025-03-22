---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS_0080_2
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS_0080_2
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS_0080_2 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS_0080_2
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS_0080_2
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS_0080_2
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS_0080_2
---

# D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS_0080_2 structure (d3d12umddi.h)

## -description

The **D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS_0080_2** structure contains rate control configuration mode-specific parameters.

## -struct-fields

### -field DataSize

Size of the referenced data, in bytes.

### -field pConfiguration_CQP

Pointer to a [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CQP_0080**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_cqp_0080.md) structure that contains the rate control structure definition for constant quantization parameter (CQP) mode.

### -field pConfiguration_CBR

Pointer to a [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CBR_0080**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_cbr_0080.md) structure that contains the rate control structure definition for constant bitrate (CBR) mode.

### -field pConfiguration_VBR

Pointer to a [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_VBR_0080**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_vbr_0080.md) structure that contains the rate control structure definition for variable bitrate (VBR) mode.

### -field pConfiguration_QVBR

Pointer to a [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_QVBR_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_qvbr_0080_2.md) structure that contains the rate control structure definition for constant quality target with constrained (variable) bitrate (QVBR) mode.

### -field pConfiguration_CQP1

Pointer to a [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CQP1_0096**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_cqp1_0096.md) structure that contains the extended rate control structure definition for constant quantization parameter (CQP) mode. Available starting with Windows 11, version 24H2 (WDDM 3.2).

### -field pConfiguration_CBR1

Pointer to a [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CBR1_0096**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_cbr1_0096.md) structure that contains the extended rate control structure definition for constant bitrate (CBR) mode. Available starting with Windows 11, version 24H2 (WDDM 3.2).

### -field pConfiguration_VBR1

Pointer to a [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_VBR1_0096**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_vbr1_0096.md) structure that contains the extended rate control structure definition for variable bitrate (VBR) mode. Available starting with Windows 11, version 24H2 (WDDM 3.2).

### -field pConfiguration_QVBR1

Pointer to a [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_QVBR1_0096**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_qvbr1_0096.md) structure that contains the extended rate control structure definition for constant quality target with variable bitrate (QVBR) mode. Available starting with Windows 11, version 24H2 (WDDM 3.2).

### -field pConfiguration_AbsoluteQPMap

Pointer to a [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_ABSOLUTE_QP_MAP_0096**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_absolute_qp_map_0096.md) structure that contains the rate control structure definition for absolute QP map mode. Available starting with Windows 11, version 24H2 (WDDM 3.2).

## -remarks

The configuration mode-specific structure to use is based on the value of **[D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_0080_2](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_0080_2.md).Mode**.

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_0080_2.md)
