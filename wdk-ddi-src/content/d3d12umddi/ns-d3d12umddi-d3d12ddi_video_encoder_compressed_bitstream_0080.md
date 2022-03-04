---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_COMPRESSED_BITSTREAM_0080
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_COMPRESSED_BITSTREAM_0080
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_COMPRESSED_BITSTREAM_0080 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_COMPRESSED_BITSTREAM_0080
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_COMPRESSED_BITSTREAM_0080
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_COMPRESSED_BITSTREAM_0080
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_COMPRESSED_BITSTREAM_0080
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_COMPRESSED_BITSTREAM_0080
---

## -description

The **D3D12DDI_VIDEO_ENCODER_COMPRESSED_BITSTREAM_0080** structure encapsulates the compressed bitstream output for the encoding operation.

## -struct-fields

### -field hDrvBuffer

Resource handle for the buffer that contains the compressed bitstream. The resource buffer size is not the available size for this encoding operation. Specifically, the available size for the current frame output in this buffer is the size of this buffer minus **Offset**.

### -field Offset

The offset into the compressed bitstream where the encoder can start adding the current frame output, in bytes.

## -remarks

The output bitstream is expected to contain the sub-region headers but not the picture, sequence, video, or other headers. It is the host's responsibility to code these other headers and generate the complete bitstream.

In sub-region frame partitioning, all sub-regions for a given frame encoding operation output must be placed in top/down, left/right order and must be contiguous.

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_STREAM_ARGUMENTS_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_encodeframe_output_stream_arguments_0080_2.md)
