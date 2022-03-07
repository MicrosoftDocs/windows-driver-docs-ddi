---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CQP_0080
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CQP_0080
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CQP_0080 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CQP_0080
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CQP_0080
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CQP_0080
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CQP_0080
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CQP_0080
---

## -description

The **D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CQP_0080** structure contains the rate control definition for constant quantization parameter (CQP) mode.

## -struct-fields

### -field ConstantQP_FullIntracodedFrame

The quantization parameter that should be used for each fully intra-encoded frame.

### -field ConstantQP_InterPredictedFrame_PrevRefOnly

The quantization parameter that should be used for each encoded frame that has inter-picture references to pictures, in display order, before the current one.

### -field ConstantQP_InterPredictedFrame_BiDirectionalRef

The quantization parameter that should be used for each encoded frame that has inter-picture references to pictures, in display order, both from the previous and next frames.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_CONFIGURATION_PARAMS_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_configuration_params_0080_2.md)
