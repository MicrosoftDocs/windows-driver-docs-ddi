---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS_0080_2
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS_0080_2
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS_0080_2 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS_0080_2
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS_0080_2
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS_0080_2
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS_0080_2
---

## -description

The **D3D12DDI_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS_0080_2** structure represents the video encoder resolution support limits for a [**D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0**](ne-d3d12umddi-d3d12ddi_video_encoder_support_flags_0083_0.md) structure.

## -struct-fields

### -field MaxSubregionsNumber

Indicates the maximum number of subregions per frame supported by the encoder for the associated resolution. **MaxSubregionsNumber** is expected to be an absolute maximum limit of subregions per frame to be coded when mode is [**D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080_BYTES_PER_SUBREGION**](ne-d3d12umddi-d3d12ddi_video_encoder_frame_subregion_layout_mode_0080.md)

### -field MaxIntraRefreshFrameDuration

Indicates the maximum number that can be used in [**D3D12DDI_VIDEO_ENCODER_INTRA_REFRESH_0080.IntraRefreshDuration**](ns-d3d12umddi-d3d12ddi_video_encoder_intra_refresh_0080.md) for the associated resolution.

### -field SubregionBlockPixelsSize

Indicates, for the associated resolution, the size in pixels of the squared regions that will be used to partition the frame for the subregion layout (slices) semantics. The resolution of the frame will be rounded up to be aligned to this value when the rame is partitioned in bloks. The configuration of the suregion partitioning will use a number of squared subregions that have their size in pixels according to the value of this member.

> [!NOTE]
>
> For HEVC encoding, this member indicates the resolution block alignment for the compressed bitstream. For example, if **SubregionBlockPixelsSize** equals 32, then *SPS.pic_width/height_in_luma_samples* must be aligned to this value and *SPS.conf_win_\*_offset/conformance_window_flag* indicate the difference between this aligned resolution and the current frame resolution indicated by [D3D12_RESOURCE_DESC.Dimension](/windows/win32/api/d3d12/ns-d3d12-d3d12_resource_desc) of the input video texture. **SubregionBlockPixelsSize** must be aligned to [D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_0083_0.MinLumaCodingUnitSize](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_hevc_0083_0.md) (minCUSize), so *SPS.pic_width/height_in_luma_samples* ends up aligned to minCUSize as required by the HEVC codec spec.

### -field QPMapRegionPixelsSize

Indicates the size in pixels of the squared regions for the associated resolution that will be affected by each of the values in the QP map buffer in absolute or delta QP modes. The resolution of the frame will be rounded up to be aligned to this value when it's partitioned in blocks for QP maps and the number of QP values in those maps will be the number of blocks of these indicated pixel size that comprise a full frame.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDIARG_VIDEO_GETCAPS_0020**](ns-d3d12umddi-d3d12ddiarg_video_getcaps_0020.md)

[**D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0**](ns-d3d12umddi-d3d12ddicaps_video_encoder_support_data_0083_0.md)
