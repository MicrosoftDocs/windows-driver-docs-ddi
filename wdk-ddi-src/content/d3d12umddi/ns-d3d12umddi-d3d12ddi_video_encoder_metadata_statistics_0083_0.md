---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_METADATA_STATISTICS_0083_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_METADATA_STATISTICS_0083_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_METADATA_STATISTICS_0083_0 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_METADATA_STATISTICS_0083_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_METADATA_STATISTICS_0083_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_METADATA_STATISTICS_0083_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_METADATA_STATISTICS_0083_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_METADATA_STATISTICS_0083_0** structure is used to provide encoding statistics for an [encoding operation](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md).

## -struct-fields

### -field AverageQP

Specifies the average quantization parameter (QP) value used for encoding this frame.

### -field IntraCodingUnitsCount

Specifies the number of intra-coded coding units used in this frame.

### -field InterCodingUnitsCount

Specifies the number of inter-coded coding units used in this frame.

### -field SkipCodingUnitsCount

Specifies the number of skip coding units used in this frame.

### -field AverageMotionEstimationXDirection

Specifies the average motion vector shift in the *X* direction.

### -field AverageMotionEstimationYDirection

Specifies the average motion vector shift in the *Y* direction.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_OUTPUT_METADATA_0083_0**](ns-d3d12umddi-d3d12ddi_video_encoder_output_metadata_0083_0.md)

[**PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md)
