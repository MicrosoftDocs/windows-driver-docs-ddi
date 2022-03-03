---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS_0082_0 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS_0082_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS_0082_0** structure represents output arguments from a call to [**PFND3D12DDI_VIDEO_ENCODE_RESOLVE_OUTPUT_METADATA_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_resolve_output_metadata_0082_0.md).

## -struct-fields

### -field ResolvedLayoutEncoderMetadataDrvBuffer

A [**D3D12DDI_VIDEO_ENCODER_ENCODE_OPERATION_METADATA_BUFFER_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_encode_operation_metadata_buffer_0080_2.md) structure in which to store the resolved metadata buffer. The user needs to read back this buffer to the CPU and cast it to [**D3D12DDI_VIDEO_ENCODER_OUTPUT_METADATA_0083_0**](ns-d3d12umddi-d3d12ddi_video_encoder_output_metadata_0083_0.md). The remaining data in the buffer is **D3D12DDI_VIDEO_ENCODER_ENCODE_OPERATION_METADATA_BUFFER_0080_2.WrittenSubregionsCount** *packed* entries of type [**D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_METADATA_0083_0**](ns-d3d12umddi-d3d12ddi_video_encoder_frame_subregion_metadata_0083_0.md).

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_METADATA_0083_0**](ns-d3d12umddi-d3d12ddi_video_encoder_frame_subregion_metadata_0083_0.md)

[**D3D12DDI_VIDEO_ENCODER_OUTPUT_METADATA_0083_0**](ns-d3d12umddi-d3d12ddi_video_encoder_output_metadata_0083_0.md)

[**PFND3D12DDI_VIDEO_ENCODE_RESOLVE_OUTPUT_METADATA_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_resolve_output_metadata_0082_0.md)
