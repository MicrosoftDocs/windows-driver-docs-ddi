---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095
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
 - D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095** structure is a comprehensive configuration structure that contains all the necessary parameters for controlling the encoding of an AV1 picture (frame).

## -struct-fields

### -field Flags

A [**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_0095_flags.md) enumeration that specifies the flags for the frame to be encoded.

### -field FrameType

A [**D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_frame_type_0095.md) enumeration that specifies the frame type being encoded.

### -field CompoundPredictionType

A [**D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE_0095**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_comp_prediction_type_0095.md) enumeration that specifies the compound prediction type to be used. Related to AV1 syntax reference_select.

### -field InterpolationFilter

A [**D3D12DDI_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS_0095**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_interpolation_filters_0095.md) enumeration that specifies the interpolation filter to be used for inter prediction on the current frame. Related to syntax interpolation_filter.

### -field FrameRestorationConfig

A [**D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_restoration_config_0095.md) structure that specifies the frame restoration configuration to be used.

### -field TxMode

A [**D3D12DDI_VIDEO_ENCODER_AV1_TX_MODE_0095**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_tx_mode_0095.md) enumeration that specifies the transform mode to be used.

### -field SuperResDenominator

Indicates the configuration for super resolution. Has to be greater than or equal to **D3D12_VIDEO_ENCODER_AV1_SUPERRES_DENOM_MIN** (as defined by the AV1 codec standard) when super resolution is enabled.

### -field OrderHint

Current frame order_hint AV1 syntax. **OrderHint** must be always passed even when not coding the order hint in the AV1 bitstream, and it must reflect the display order of the frame.

### -field PictureIndex

The unique picture index for this frame that will be used to uniquely identify it as a reference for future frames. This parameter is not related in any way to the AV1 standard syntax, but merely used for D3D API client implementation tracking instead.

The API Client should initialize this value at 0 for the first [**D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_KEY_FRAME**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_frame_type_0095.md) and increment it by one on each subsequent frame until the next **D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_KEY_FRAME**, when it should be reset to zero and follow the same process.

**OrderHint** can't be used for this purpose as it has a max range of ```[0..2^(OrderHintBitsMinus1+1)]```, which can wrap around and not work as a unique identifier of the frames and their references.

### -field TemporalLayerIndexPlus1

Picture temporal layer index plus one. A value of zero indicates temporal scalability not used. This value must be within the range [0..[D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095]( ns-d3d12umddi-d3d12ddi_video_encoder_av1_codec_configuration_support_0095.md).MaxTemporalLayers].

### -field SpatialLayerIndexPlus1

Picture spatial layer index plus one. A value of zero indicates spatial scalability isn't used. This value must be within the range [0..D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095.MaxSpatialLayers].

### -field ReferenceFramesReconPictureDescriptors[8]

An array of [**D3D12DDI_VIDEO_ENCODER_AV1_REFERENCE_PICTURE_DESCRIPTOR_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_reference_picture_descriptor_0095.md) structures that describes the current state snapshot of the complete (ie. including frames that are not used by current frame but used by future frames, etc) DPB buffer kept in [D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_DESC_0082_0](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_desc_0082_0.md).ReferenceFrames. The reference indices (ie. last, altref, etc) map from past/future references into this descriptors array. The AV1 codec allows up to 8 references in the DPB.

This array of descriptors, in turn, maps a reference picture for this frame into a resource index in the reconstructed pictures array D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_DESC_0082_0.ReferenceFrames.

The size of this array always matches D3D12_VIDEO_ENCODER_PICTURE_CONTROL_DESC.ReferenceFrames.NumTextures for the associated [*EncodeFrame*](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md) command.

### -field ReferenceIndices[7]

Corresponds to the ref_frame_idx[i] AV1 syntax. For a reference type i, **ReferenceIndices**[i] indicates an index between [0..7] into **ReferenceFramesReconPictureDescriptors** where the current frame i-th reference type is stored in the DPB. In other words **ReferenceFramesReconPictureDescriptors**[**ReferenceIndices**[i]] contains the DPB descriptor for the i-th reference type.

The i-th entry of **ReferenceIndices**[] corresponds to each reference type as follows.

| Index i | Reference type | ReferenceFramesReconPictureDescriptors[ReferenceIndices[i]] |
| --- | --- | --- |
| 0 | Last | DPB Descriptor for Last |
| 1 | Last2 | DPB Descriptor for Last2 |
| 2 | Last3 | DPB Descriptor for Last3 |
| 3 | Golden | DPB Descriptor for Golden |
| 4 | Bwdref | DPB Descriptor for Bwdref |
| 5 | Altref | DPB Descriptor for Altref |
| 6 | Altref2 | DPB Descriptor for Altref2 |

### -field PrimaryRefFrame

Corresponds to the AV1 element syntax primary_ref_frame in uncompressed_header(). Specifies which reference frame contains the CDF values and other state that must be loaded at the start of the frame. The allowed range is [0..7] and the values corresponds as follows:

| PrimaryRefFrame value | AV1 syntax value (primary_ref_frame) | Reference frame selected |
| --- | --- | --- |
| 0 | 0 | Last    |
| 1 | 1 | Last2   |
| 2 | 2 | Last3   |
| 3 | 3 | Golden  |
| 4 | 4 | Bwdref  |
| 5 | 5 | Altref  |
| 6 | 6 | Altref2 |
| 7 | 7 (PRIMARY_REF_NONE) | None |

### -field RefreshFrameFlags

Corresponds to the refresh_frame_flags AV1 syntax element.

### -field LoopFilter

A [**D3D12DDI_VIDEO_ENCODER_CODEC_AV1_LOOP_FILTER_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_av1_loop_filter_config_0095.md) structure that specifies the loop filter parameters to be used.

### -field LoopFilterDelta

A [**D3D12DDI_VIDEO_ENCODER_CODEC_AV1_LOOP_FILTER_DELTA_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_av1_loop_filter_delta_config_0095.md) structure that specifies the loop filter delta parameters to be used.

### -field Quantization

A [**D3D12DDI_VIDEO_ENCODER_CODEC_AV1_QUANTIZATION_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_av1_quantization_config_0095.md) structure that specifies the quantization parameters to be used.

### -field QuantizationDelta

A [**D3D12DDI_VIDEO_ENCODER_CODEC_AV1_QUANTIZATION_DELTA_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_av1_quantization_delta_config_0095.md) structure that specifies the quantization delta parameters to be used.

### -field CDEF

A [**D3D12DDI_VIDEO_ENCODER_AV1_CDEF_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_cdef_config_0095.md) structure that specifies the constrained directional enhancement filtering (CDEF) parameters to be used.

### -field QPMapValuesCount

Contains the number of elements present in **pRateControlQPMap**. This value must match the number of coding blocks in the frame, rounding up the frame resolution to the closest aligned values.

### -field pRateControlQPMap

Array containing, in row/column scan order, the QP map values to use on each squared region for this frame. The QP map dimensions can be calculated using the current resolution and [D3D12DDI_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS_0080_2](ns-d3d12umddi-d3d12ddi_video_encoder_resolution_support_limits_0080_2.md).QPMapRegionPixelsSize conveying the squared region sizes. The range for Delta QP values is [-255;255].

### -field CustomSegmentation

A [**D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_segmentation_config_0095.md) structure that specifies the custom segmentation parameters to be used. Only used when [**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_0095_FLAG_ENABLE_FRAME_SEGMENTATION_CUSTOM**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_0095_flags.md) is set for the current frame.

### -field CustomSegmentsMap

Only used when **D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_0095_FLAG_ENABLE_FRAME_SEGMENTATION_CUSTOM** is set for the current frame. A [**D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MAP_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_segmentation_map_0095.md) structure that specifies the custom segmentation map to be used if **CustomSegmentation.UpdateMap** is set. Otherwise, the segment map is inherited from the reference frame.

## -remarks

### DPB Management expectations

The following is the contract the API client and the driver must conform to when using this API:

1. When encoding [**D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_KEY_FRAME**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_frame_type_0095.md):

   * **PrimaryRefFrame** must be 7 (PRIMARY_REF_NONE)
   * **RefreshFrameFlags** must be 0xFF (conforming to the AV1 codec standard bitstream syntax)
   * For all array entries in **ReferenceFramesReconPictureDescriptors**, **ReconstructedPictureResourceIndex** must be set to D3D12_VIDEO_ENCODER_AV1_INVALID_DPB_RESOURCE_INDEX
   * The values in **ReferenceIndices**[7] are indistinct as any value [0..7] will point to an unused DPB slot in **ReferenceFramesReconPictureDescriptors** as per the point above.
   * [**D3D12DDI_VIDEO_ENCODE_REFERENCE_FRAMES_0082_0**](ns-d3d12umddi-d3d12ddi_video_encode_reference_frames_0080.md) will be filled as:
     * **NumTexture2Ds** = 0
     * **ppTexture2Ds** = NULL
     * **pSubresources** = NULL

2. When encoding a frame type with references (ie. SWITCH/INTER):

   * **PrimaryRefFrame** specifies which reference frame contains the CDF values and other state that must be loaded at the start of the frame.
   * **RefreshFrameFlags** must be set accordingly to indicate on which **ReferenceFramesReconPictureDescriptors** DPB slots the current encoded frame reconstructed picture will be placed after encoding execution. This value must match exactly what the API client will code for refresh_frame_flags AV1 syntax element in the associated picture header for the current frame.
   * The array entries in **ReferenceFramesReconPictureDescriptors** for the current frame will follow exactly what **RefreshFrameFlags** indicated for the previous frame.
      * For example: if **RefreshFrameFlags** indicates the current frame N will be placed in slots 2, 3 and 6, then in the next [*EncodeFrame*](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md) call for frame N+1, the **ReconstructedPictureResourceIndex** parameter in the entries **ReferenceFramesReconPictureDescriptors**[1], **ReferenceFramesReconPictureDescriptors**[2], **ReferenceFramesReconPictureDescriptors**[5] parameter must point to frame N reconstructed picture in [**D3D12DDI_VIDEO_ENCODE_REFERENCE_FRAMES_0080**](ns-d3d12umddi-d3d12ddi_video_encode_reference_frames_0080.md).

      * Note this includes considering **RefreshFrameFlags**=0xFF for **D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_KEY_FRAME** as well, by marking all **ReferenceFramesReconPictureDescriptors** entries pointing to the KEY frame reconstructed picture.
      * If a (non key frame) picture won't be marked with [**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_FLAG_0080_USED_AS_REFERENCE_PICTURE**](ne-d3d12umddi-d3d12ddi_video_encoder_picture_control_flags_0080.md), their **RefreshFrameFlags** must be zero to indicate this.
   * The values in **ReferenceIndices**[7] are within [0..7] and point to DPB slots in **ReferenceFramesReconPictureDescriptors**.
   * The values of **ReferenceIndices**[7] must match exactly what the API client codes in the picture header for ref_frame_idx.
   * As per AV1 syntax definition of ref_frame_idx there is no requirement that the array entry values must be unique.
   * If **ReferenceFramesReconPictureDescriptors**[**ReferenceIndices**[i]]. **ReconstructedPictureResourceIndex** == D3D12_VIDEO_ENCODER_AV1_INVALID_DPB_RESOURCE_INDEX
      * This indicates the reference picture i-th won't be used for the current frame and must be ignored.
   * Otherwise (Valid **ReferenceFramesReconPictureDescriptors**[**ReferenceIndices**[i]]. **ReconstructedPictureResourceIndex**)
      * This indicates the reference i-th will point to the DPB slot **ReferenceIndices**[i] and the reconstructed picture to be used is [**D3D12DDI_VIDEO_ENCODE_REFERENCE_FRAMES_0080**](ns-d3d12umddi-d3d12ddi_video_encode_reference_frames_0080.md).**ppTexture2Ds**[**ReferenceFramesReconPictureDescriptors**[**ReferenceIndices**[i]].**ReconstructedPictureResourceIndex**]
   * [**D3D12DDI_VIDEO_ENCODE_REFERENCE_FRAMES_0080**](ns-d3d12umddi-d3d12ddi_video_encode_reference_frames_0080.md) will be filled as:

      * **NumTexture2Ds** = {number of unique values of **ReferenceFramesReconPictureDescriptors**.**ReconstructedPictureResourceIndex**[j] != D3D12_VIDEO_ENCODER_AV1_INVALID_DPB_RESOURCE_INDEX for j in {0..7} }
      * **ppTexture2Ds** = { compact array (no null entries) containing the reconstructed picture from the previously encoded frames that will be used as references }
      * [Texture Array mode only] **pSubresources** = { compact array (no null entries) containing the subresource index of the texture array from the previously encoded frames that will be used as references }

3. When encoding a frame type without references but without clearing the DPB (ie. INTRA_ONLY)

   * **PrimaryRefFrame** must be 7 (PRIMARY_REF_NONE)
   * **RefreshFrameFlags** must be set accordingly to indicate on which **ReferenceFramesReconPictureDescriptors** DPB slots the current encoded frame reconstructed picture will be placed after encoding execution. This value must match exactly what the API client will code for refresh_frame_flags AV1 syntax element in the associated picture header for the current frame.
   * The array entries in **ReferenceFramesReconPictureDescriptors** for the current frame will follow exactly what RefreshFrameFlags indicated for the previous frame.
   * The values in **ReferenceIndices**[7] are ignored as the intra-only frame doesn't use any references.
   * [**D3D12DDI_VIDEO_ENCODE_REFERENCE_FRAMES_0080**](ns-d3d12umddi-d3d12ddi_video_encode_reference_frames_0080.md) contains the DPB snapshot and will be filled as:

      * **NumTexture2Ds** = {number of *unique* values of **ReferenceFramesReconPictureDescriptors**.**ReconstructedPictureResourceIndex**[j] != D3D12_VIDEO_ENCODER_AV1_INVALID_DPB_RESOURCE_INDEX for j in {0..7} }
      * **ppTexture2Ds** = { compact array (no null entries) containing the reconstructed picture from the previously encoded frames referred to by **ReferenceFramesReconPictureDescriptors**.**ReconstructedPictureResourceIndex**[j] for j in {0..7} }
      * [Texture Array mode only] **pSubresources** = { compact array (no null entries) containing the subresource index of the texture array from the previously encoded frames referred to by **ReferenceFramesReconPictureDescriptors**.**ReconstructedPictureResourceIndex**[j] for j in {0..7} }

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_codec_data_0082_0.md)
