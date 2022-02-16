---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_OUTPUT_METADATA_0083_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_OUTPUT_METADATA_0083_0
ms.date: 02/16/20221
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_OUTPUT_METADATA_0083_0 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_OUTPUT_METADATA_0083_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_OUTPUT_METADATA_0083_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_OUTPUT_METADATA_0083_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_OUTPUT_METADATA_0083_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_OUTPUT_METADATA_0083_0** structure represents the metadata of the output of an [encoding operation](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md).

## -struct-fields

### -field EncodeErrorFlags

A UINT64 value that represents flag(s) from the [**D3D12DDI_VIDEO_ENCODER_ENCODE_ERROR_FLAGS_0082_0**](ne-d3d12umddi-d3d12ddi_video_encoder_encode_error_flags_0082_0.md) enumeration that specify information about the encode execution status.

### -field EncodeStats

A [**D3D12DDI_VIDEO_ENCODER_METADATA_STATISTICS_0083_0**](ns-d3d12umddi-d3d12ddi_video_encoder_metadata_statistics_0083_0.md) structure that provides statistics about the encode execution.

### -field EncodedBitstreamWrittenBytesCount

The number of bytes that were written into [**D3D12DDI_VIDEO_ENCODER_COMPRESSED_BITSTREAM_0080.hDrvBuffer**](ns-d3d12umddi-d3d12ddi_video_encoder_compressed_bitstream_0080.md) plus **D3D12DDI_VIDEO_ENCODER_COMPRESSED_BITSTREAM_0080.Offset**.

### -field WrittenSubregionsCount

The number of sub-regions used to encode the current frame. This value must be coherent with the settings specified in [**D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC_0082_0.FrameSubregionsLayoutData**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_control_desc_0082_0.md); that is, if a number of sub-regions was previously specified, **WrittenSubregionsCount** should match that value. If another mode was used, the driver uses this field to report the final number of sub-regions. If the output is one full frame, then there is only one sub-region.

## -remarks

**D3D12DDI_VIDEO_ENCODER_OUTPUT_METADATA_0083_0** and its child structures are aligned to a 64-bit access boundary for use with [**PFND3D12DDI_SET_PREDICATION**](nc-d3d12umddi-pfnd3d12ddi_set_predication.md).

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_resolve_metadata_output_arguments_0082_0.md)

[**PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md)

[**PFND3D12DDI_VIDEO_ENCODE_RESOLVE_OUTPUT_METADATA_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_resolve_output_metadata_0082_0.md)

[**PFND3D12DDI_SET_PREDICATION**](nc-d3d12umddi-pfnd3d12ddi_set_predication.md)
