---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095 structure.
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
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095
---

## -description

If a [**D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_post_encode_values_0095_flags.md) value is reported for its respective structure, the driver must write the value after [*EncodeFrame*](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md) execution with or without modifications (copy API client input) done by the driver. Otherwise, the driver must copy the values from the associated API Client input when calling *EncodeFrame*.

## -struct-fields

### -field CompoundPredictionType

Associated flag is **D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_COMPOUND_PREDICTION_MODE**.

### -field LoopFilter

Associated flag is **D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_LOOP_FILTER**.

### -field LoopFilterDelta

Associated flag is **D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_LOOP_FILTER_DELTA**.

### -field Quantization

Associated flag is **D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_QUANTIZATION**.

### -field QuantizationDelta

Associated flag is **D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_QUANTIZATION_DELTA**.

### -field CDEF

Associated flag is **D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_CDEF_DATA**.

### -field SegmentationConfig

This member operates in different modes depending the segmentation mode selected.

* If [**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_0095_FLAG_ENABLE_FRAME_SEGMENTATION_AUTO**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_0095_flags.md) is on for the current frame, the driver:
  * Calculates and writes **SegmentationConfig**, which will be used by the API Client to code the segmentation_params() syntax in the frame header.
  * Calculates and writes the read_segment_id() map information directly in the compressed bitstream.
* If **D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAG_ENABLE_FRAME_SEGMENTATION_CUSTOM** is on for the current frame, the driver:
  * Copy here the **SegmentationConfig** sent by the API Client in the encode frame parameters for API Client to code the segmentation_params() syntax in the frame header.
  * Copy the read_segment_id() map sent by the API Client in the encode frame parameters directly in the compressed bitstream.
* Otherwise (both segmentation modes are off):
  * The driver should write all zeroes.
  * API Client will write segmentation_enabled = 0 accordingly in the segmentation_params() section of the frame header.

### -field PrimaryRefFrame

Associated flag is **D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAG_PRIMARY_REF_FRAME**. If the flag was set, the driver controls the selection of the primary reference frame from which the segment id map, CDF, etc are inherited from.

When used together with [**D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_AUTO_SEGMENTATION**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_feature_0095_flags.md), allows the driver to force a value other than PRIMARY_REF_NONE when applicable, giving the driver full control of the AV1 syntax: segmentation_update_map, segmentation_temporal_update and segmentation_update_data in segmentation_params().

### -field ReferenceIndices[7]

When the flag is reported, the driver may reorder/remap (but not change the number of references) the **ReferenceIndices** array, based on the user input [**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_codec_data_0095.md)**.ReferenceIndices**. Otherwise, the driver must copy each array entry of this parameter as-is from **D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095.ReferenceIndices**.

API Client will write the picture header ref_frame_idx AV1 syntax from this output parameter.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_codec_configuration_support_0095.md)

[**D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_post_encode_values_0095_flags.md)
