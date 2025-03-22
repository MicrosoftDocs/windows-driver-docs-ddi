---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_ABSOLUTE_QP_MAP_0096
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_ABSOLUTE_QP_MAP_0096
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_ABSOLUTE_QP_MAP_0096 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_ABSOLUTE_QP_MAP_0096
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
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_ABSOLUTE_QP_MAP_0096
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_ABSOLUTE_QP_MAP_0096
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_ABSOLUTE_QP_MAP_0096
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_ABSOLUTE_QP_MAP_0096
---

# D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_ABSOLUTE_QP_MAP_0096 structure (d3d12umddi.h)

## -description

The **D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_ABSOLUTE_QP_MAP_0096** structure specifies the rate control parameters when an absolute QP map is used.

## -struct-fields

### -field QualityVsSpeed

The quality versus speed trade-off. This value must be in the range [0, D3D12_FEATURE_DATA_VIDEO_ENCODER_SUPPORT1.MaxQualityVsSpeed]. The lower the value, the faster the encode operation.

The settings associated to each of the levels exposed by **QualityVsSpeed** must only refer to hardware/driver implementation optimizations and heuristics that aren't related to specific codec configurations or encoding tools selection, which are already independently exposed in the D3D12 API to the user individually. Please note that other codec configurations and codec encoding tools exposed through this API may also affect quality and speed.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_configuration_params_0080_2.md)

[**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_FLAGS_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_rate_control_flags_0080.md)
