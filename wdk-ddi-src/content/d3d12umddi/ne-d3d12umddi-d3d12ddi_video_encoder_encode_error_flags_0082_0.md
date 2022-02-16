---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_ENCODE_ERROR_FLAGS_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_ENCODE_ERROR_FLAGS_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_ENCODE_ERROR_FLAGS_0082_0 enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_ENCODE_ERROR_FLAGS_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_ENCODE_ERROR_FLAGS_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_ENCODE_ERROR_FLAGS_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_ENCODE_ERROR_FLAGS_0082_0** enumeration specified error(s) encounted during the associated [**PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md) command execution.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_ENCODE_ERROR_FLAG_0082_0_NO_ERROR

No errors occurred.

### -field D3D12DDI_VIDEO_ENCODER_ENCODE_ERROR_FLAG_0082_0_CODEC_PICTURE_CONTROL_NOT_SUPPORTED

The specified codec picture control description is not supported.

### -field D3D12DDI_VIDEO_ENCODER_ENCODE_ERROR_FLAG_0082_0_SUBREGION_LAYOUT_CONFIGURATION_NOT_SUPPORTED

The specified sub-region layout configuration is not supported.

### -field D3D12DDI_VIDEO_ENCODER_ENCODE_ERROR_FLAG_0082_0_INVALID_REFERENCE_PICTURES

The specified reference pictures are invalid.

### -field D3D12DDI_VIDEO_ENCODER_ENCODE_ERROR_FLAG_0082_0_RECONFIGURATION_REQUEST_NOT_SUPPORTED

The requested reconfiguration is not supported.

### -field D3D12DDI_VIDEO_ENCODER_ENCODE_ERROR_FLAG_0082_0_INVALID_METADATA_BUFFER_SOURCE

The metadata buffer source is invalid.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_OUTPUT_METADATA_0083_0**](ns-d3d12umddi-d3d12ddi_video_encoder_output_metadata_0083_0.md)
