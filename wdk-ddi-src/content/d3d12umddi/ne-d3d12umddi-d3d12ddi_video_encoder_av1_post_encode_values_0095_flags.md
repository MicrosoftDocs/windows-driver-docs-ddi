---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAGS
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAGS
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAGS enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAGS
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAGS
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAGS
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAGS** enumeration specifies which AV1 encoding features the underlying encoder is able to override (partially or totally) the associated AV1 syntax values or honor API Client exact configuration input otherwise.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_NONE:0

### -field D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_QUANTIZATION:0x1

Related to [**D3D12DDI_VIDEO_ENCODER_CODEC_AV1_QUANTIZATION_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_av1_quantization_config_0095.md) values. Used to code quantization_params().

### -field D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_QUANTIZATION_DELTA:0x2

Related to [**D3D12DDI_VIDEO_ENCODER_CODEC_AV1_QUANTIZATION_DELTA_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_av1_quantization_delta_config_0095.md) values. Used to code delta_q_params().

### -field D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_LOOP_FILTER:0x4

Related to [**D3D12DDI_VIDEO_ENCODER_CODEC_AV1_LOOP_FILTER_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_av1_loop_filter_config_0095.md) values. Used to code AV1 syntax loop_filter_params().

### -field D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_LOOP_FILTER_DELTA:0x8

Related to [**D3D12DDI_VIDEO_ENCODER_CODEC_AV1_LOOP_FILTER_DELTA_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_av1_loop_filter_delta_config_0095.md) values. Used to code AV1 syntax delta_lf_params().

### -field D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_CDEF_DATA:0x10

Related to [**D3D12DDI_VIDEO_ENCODER_AV1_CDEF_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_cdef_config_0095.md) values. Used to code AV1 syntax cdef_params().

### -field D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_CONTEXT_UPDATE_TILE_ID:0x20

Related to the **ContextUpdateTileId** member in [**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_SUBREGIONS_LAYOUT_DATA_TILES_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_subregions_layout_data_tiles_0095.md). Used to code AV1 element syntax context_update_tile_id in tile_info().

### -field D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_COMPOUND_PREDICTION_MODE:0x40

Related to [**D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE_0095**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_comp_prediction_type_0095.md) values.

When API Client selects **D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE_COMPOUND_REFERENCE** and this flag is set, the driver will return **D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE** in post encode values. The returned value must be used to code reference_select = 0 (SINGLE) or reference_select = 1 (COMPOUND) syntax accordingly.

When API Client selects **D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE_COMPOUND_SINGLE** and this flag is set, the driver will return **D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE_COMPOUND_SINGLE** and reference_select must be coded as 0 (SINGLE).

### -field D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_PRIMARY_REF_FRAME:0x80

Related to the **PrimaryRefFrame** element in [**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_codec_data_0095.md). Used to code AV1 element syntax primary_ref_frame in uncompressed_header().

### -field D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_REFERENCE_INDICES:0x100

When the flag is reported by the driver, the driver may reorder/remap (but not change the number of references) of the [**D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_post_encode_values_0095.md)**.ReferenceIndices** array output, based on the user input [**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_codec_data_0095.md)**.ReferenceIndices**. Otherwise, the driver must copy each array entry of this post encode output parameter as-is from **D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095.ReferenceIndices**.

API Client will write the picture header ref_frame_idx AV1 syntax from this output parameter.

## -remarks

When the bitflag is SET for a given feature, the driver receives the related API Client input and is able to override all or certain parameters of the associated structure with the given reported flag, which will then write back in [**D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_post_encode_values_0095.md) with the final values for the API Client to repack the AV1 headers accordingly. API Client can compare this to the associated input structure to determine the driver changes, if any.

When the bitflag is NOT SET for a given feature, the driver honors the related API Client input exactly and copies the input values in **D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095**. In this way, the client can always copy the post encode values to pack the headers directly.

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_codec_configuration_support_0095.md)
