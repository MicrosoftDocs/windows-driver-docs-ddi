---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_METADATA_0083_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_METADATA_0083_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_METADATA_0083_0 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_METADATA_0083_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_METADATA_0083_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_METADATA_0083_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_METADATA_0083_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_METADATA_0083_0** structure represents subregion metadata of a video encoder frame.

## -struct-fields

### -field bSize

Output field in which to store the sizes of each sub-region, in bytes. Sub-regions sizes must include the sub-region initial padding, header, and payload.

### -field bStartOffset

Output field in which to store the padding size that needs to be skipped at the beginning of every subregion, in bytes. This padding size is included in **bSize**.

For example, let *pFrameSubregionsSizes* be an array of **bSize** bytes for each slice. With **bStartOffset** and *pFrameSubregionsSizes*, the user can extract individual subregions from the output bitstream buffer by calculating the *i*th sub-region start offset as ```pBuffer + FrameStartOffset + sum j = (0, (i-1)){pFrameSubregionsSizes[j]} + pFrameSubregionsStartOffsets[i]``` and reading ```pFrameSubregionsSizes[i]``` bytes.

### -field bHeaderSize

Output field in which to write the sizes in bits of each sub-region header.

With **bHeaderSize**, in addition to extracting the full sub-region from the bitstream as explained above, the user can extract the sub-regions payload and headers directly without needing to parse the full sub-region bitstream.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_resolve_metadata_output_arguments_0082_0.md)
