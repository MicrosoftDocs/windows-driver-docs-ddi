---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAGS
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAGS
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAGS enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAGS
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAGS
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAGS
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAGS** enumeration is a bitwise OR of values that report the encoding capabilities of the AV1 codec.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_NONE:0x0

Indicates that no features are supported.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_128x128_SUPERBLOCK:0x1

Indicates whether support is available for 128x128 Superblocks.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_FILTER_INTRA:0x2

Indicates whether support is available for intra prediction filter.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_INTRA_EDGE_FILTER:0x4

Indicates whether support is available for intra edge filtering process.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_INTERINTRA_COMPOUND:0x8

Indicates whether support is available for interintra, where the mode info for inter blocks may contain the syntax element interintra. A value of 0 specifies that the syntax element interintra will not be present.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_MASKED_COMPOUND:0x10

Indicates whether support is available for masked compound, where the mode info for inter blocks may contain the syntax element compound_type. A value of 0 specifies that the syntax element compound_type will not be present.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_WARPED_MOTION:0x20

A value of 1 indicates that the syntax element motion_mode may be present. A value of 0 indicates the syntax element motion_mode will not be present (this means that LOCALWARP cannot be signaled if this flag is equal to 0).

Related to AV1 syntax enable_warped_motion in the sequence header.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_DUAL_FILTER:0x40

Indicates whether support is available for dual filter mode, where the inter prediction filter type may be specified independently in the horizontal and vertical directions. If the flag is equal to 0, only one filter type may be specified, which is then used in both directions.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_JNT_COMP:0x80

Indicates whether support is available for the scenario where distance weights process may be used for inter prediction.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_FORCED_INTEGER_MOTION_VECTORS:0x100

Indicates whether support is available for using the syntax element force_integer_mv.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_SUPER_RESOLUTION:0x200

Indicates whether support is available for super resolution.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_LOOP_RESTORATION_FILTER:0x400

Indicates whether support is available for loop restoration filtering.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_PALETTE_ENCODING:0x800

Indicates whether support is available for frame level control on palette encoding; a value of 0 indicates that palette encoding is never used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_CDEF_FILTERING:0x1000

Indicates whether support is available for constrained directional enhancement filtering.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_INTRA_BLOCK_COPY:0x2000

Indicates whether intra block copy is supported or not at frame level. Same syntax as AV1 spec.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_FRAME_REFERENCE_MOTION_VECTORS:0x4000

Indicates whether support is available for use_ref_frame_mvs to be configured on a per frame basis. A value of 0 specifies that use_ref_frame_mvs syntax element will not be used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_ORDER_HINT_TOOLS:0x8000

Indicates whether support is available for usage of tools based on the values of order hints. A value of 0 indicates that tools based on order hints are not supported and can't be enabled.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_AUTO_SEGMENTATION:0x10000

Indicates whether the driver can perform segmentation without API Client input and return segmentation_params() information in D3D12_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES. Driver will write the segment map in the compressed bitstream.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_CUSTOM_SEGMENTATION:0x20000

Indicates whether the driver supports the API Client passing customized segmentation segmentation_params() as well as the segment map and driver will honor exactly.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_LOOP_FILTER_DELTAS:0x40000

Indicates whether the driver supports use of loop filter deltas. Related to loop_filter_delta_enabled AV1 syntax in loop_filter_params().

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_QUANTIZATION_DELTAS:0x80000

Indicates whether the driver supports use of quantization delta syntax.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_QUANTIZATION_MATRIX:0x100000

Indicates whether the driver supports use of quantization matrix syntax.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_REDUCED_TX_SET:0x200000

Indicates whether driver supports setting reduced_tx_set in the frame header or must be always set to zero.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_MOTION_MODE_SWITCHABLE:0x400000

Indicates whether driver supports setting is_motion_mode_switchable in the frame header or must be always set to zero.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_ALLOW_HIGH_PRECISION_MV:0x800000

Indicates whether driver supports setting allow_high_precision_mv in the frame header or must be always set to zero.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_SKIP_MODE_PRESENT:0x1000000

Indicates whether driver supports setting skip_mode_present in the frame header or must be always set to zero.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_DELTA_LF_PARAMS:0x2000000

Indicates whether the driver supports use of loop filter delta params syntax. Related to delta_lf_params() AV1 syntax.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_codec_configuration_support_0095.md)
