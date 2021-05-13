---
UID: NS:dxva._DXVA_PicParams_AV1
tech.root: display
title: DXVA_PicParams_AV1
ms.date: 05/13/2021
targetos: Windows
description: The DXVA_PicParams_AV1 structure provides the picture-level parameters of a compressed picture for AV1 video decoding.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dxva.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: DXVA_PicParams_AV1, *LPDXVA_PicParams_AV1
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dxva.h
api_name:
 - _DXVA_PicParams_AV1
 - LPDXVA_PicParams_AV1
 - DXVA_PicParams_AV1
f1_keywords:
 - _DXVA_PicParams_AV1
 - dxva/_DXVA_PicParams_AV1
 - LPDXVA_PicParams_AV1
 - dxva/LPDXVA_PicParams_AV1
 - DXVA_PicParams_AV1
 - dxva/DXVA_PicParams_AV1
dev_langs:
 - c++
---

## -description

The DXVA_PicParams_AV1 structure provides the picture-level parameters of a compressed picture for AV1 video decoding.

## -struct-fields

### -field width

Coded width of the current frame. Corresponds to the frame_width_minus_1 syntax element. See Remarks.

### -field height

Coded height of the current frame. Corresponds to the frame_height_minus_1 syntax element.  See Remarks.

### -field max_width

### -field max_height

### -field CurrPicTextureIndex

The destination frame buffer/surface index for the decoded picture.

### -field superres_denom

When superres is enabled, this field specifies the denominator for computing the updated frame width. This corresponds to the SuperresDenom value from the AV1 specification. When superres is not enabled, this value shall be 8.

### -field bitdepth

The bit depth of the luma and chroma decoded samples. The allowed values are restricted by the profile value.

### -field seq_profile

The profile of the AV1 bitstream. This corresponds to the syntax element: seq_profile. The AV1 video coding format defines the following profiles:

| Profile | Meaning |
| ------- | ------- |
| profile 0 | Supports 4:2:0 chroma sampling with 8 or 10 bits per sample and monochrome formats. |
| profile 1 | Supports 4:4:4 chroma sampling with 8 or 10 bits per sample.
| profile 2 | Supports 4:2:0, 4:2:2, or 4:4:4 chroma sampling at 8, 10 or 12 bits per sample and monochrome formats. |

### -field tiles

Contains information specific to tiles.

### -field tiles.cols

The number of tiles across a frame. This field corresponds to 2^TileColsLog2 from the AV1 specification.

### -field tiles.rows

The number of tiles down a frame. This field corresponds to 2^TileRowsLog2 from the AV1 specification.

### -field tiles.context_update_id

Specifies which tile to use for CDF update. This corresponds to the syntax element named context_update_tile_id from the AV1 specification.

### -field tiles.widths

The widths of each tile, in units of superblocks.  Only the first 2^cols_log2 widths entries are valid. This field corresponds to the tileWidthSb variable from the AV1 specification.

### -field tiles.heights

The heights of each tile, in units of superblocks. Only the first 2^rows_log2 heights entries are valid. This field corresponds to the tileHeightSb variable from the AV1 specification.

### -field coding

The coding tools.

### -field coding.use_128x128_superblock

When equal to 1, indicates that superblocks contain 128x128 luma samples; otherwise, superblocks contain 64x64 luma samples. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field coding.intra_edge_filter

Specifies whether the intra edge filtering process should be enabled. This field corresponds to the syntax element named enable_intra_edge_filter from the AV1 specification.

### -field coding.interintra_compound

When equal to 1, indicates that the mode info for inter blocks may contain the syntax element interintra; otherwise, the interintra syntax element will not be present. This field corresponds to the syntax element named enable_interintra_compound from the AV1 specification.

### -field coding.masked_compound

When equal to 1, indicates that the mode info for inter blocks may contain the syntax element compound_type; otherwise, the compound_type syntax element will not be present. This field corresponds to the syntax element named enable_masked_compound from the AV1 specification.

### -field coding.warped_motion

When equal to 1, indicates that the syntax element motion_mode may be present. This field corresponds to the syntax element named allow_warped_motion from the AV1 specification.

### -field coding.dual_filter

When equal to 1, indicates that the inter prediction filter type may be specified independently in the horizontal and vertical directions; otherwise, only one filter type may be specified. This field corresponds to the syntax element named enable_dual_filter from the AV1 specification.

### -field coding.jnt_comp

When equal to 1, indicates that the distance weights process may be used for inter prediction. This field corresponds to the syntax element named enable_jnt_comp from the AV1 specification.

### -field coding.screen_content_tools

When equal to 1, indicates that intra blocks may use palette encoding; otherwise, palette encoding will not be used. This field corresponds to the syntax element named allow_screen_content_tools from the AV1 specification.

### -field coding.integer_mv

When equal to 1, indicates that motion vectors will always be integers. This field corresponds to the syntax element named force_integer_mv from the AV1 specification.

### -field coding.cdef

When equal to 1, indicates that Constrained Directional Enhancement Filter (CDEF) filtering may be enabled. This field corresponds to the syntax element named enable_cdef from the AV1 specification.

### -field coding.restoration

When equal to 1, indicates that loop restoration filtering may be enabled. This field corresponds to the syntax element named enable_restoration from the AV1 specification.

### -field coding.film_grain

When equal to 1, indicates that film grain processing may be enabled. This field corresponds to the syntax element named film_grain_params_present from the AV1 specification.

### -field coding.intrabc

When equal to 1, indicates that intra block copy may be used. This field corresponds to the syntax element named allow_intrabc from the AV1 specification.

### -field coding.high_precision_mv

When equal to 1, indicates that motion vectors are specified to eighth pel precision; otherwise, motion vectors are specified to quarter pel precision. This field corresponds to the syntax element named allow_high_precision_mv from the AV1 specification.

### -field coding.switchable_motion_mode

When equal to 1, indicates that only the SIMPLE motion mode may be used. This field corresponds to the syntax element named is_motion_mode_switchable from the AV1 specification.

### -field coding.filter_intra

When equal to 1, indicates that the use_filter_intra syntax element may be present. This field corresponds to the syntax element named enable_filter_intra from the AV1 specification.

### -field coding.disable_frame_end_update_cdf

Specifies whether the CDF arrays are saved in the symbol decoder exit process. This field corresponds to the syntax element of the same name from the AV1 specification.  

### -field coding.disable_cdf_update

Specifies whether the CDF update in the symbol decoding process should be disabled. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field coding.reference_mode

Controls the mode used for reference frame prediction.  Can be one of the following values which correspond with the reference mode from the AV1 decoding process:

| reference_mode | Name of reference_mode |
| -------------- | ---------------------- |
| 0              | SINGLE_REFERENCE       |
| 1              | REFERENCE_MODE_SELECT  |

### -field coding.skip_mode

Indicates whether skip mode syntax can be specified in compound prediction. This field corresponds to the skip_mode_present syntax element from the AV1 specification.

### -field coding.reduced_tx_set

Specifies whether the frame uses a restricted set of transform types. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field coding.superres

Specifies whether the frame uses super resolution. This field corresponds to the syntax element named use_superres from the AV1 specification.

### -field coding.tx_mode

Specifies how the transform size is determined. This field corresponds to the variable of the same name from the AV1 specification. It can take on one of the following values, as specified in the AV1 specification:

| TxMode value | Name of TxMode  |
| ------------ | --------------  |
| 0            | ONLY_4X4        |
| 1            | TX_MODE_LARGEST |
| 2            | TX_MODE_SELECT  |

### -field coding.use_ref_frame_mvs

Specifies whether motion vectors from the previous frame should be used for the current frame. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field coding.enable_ref_frame_mvs

Specifies whether use_ref_frame_mvs is disabled for the entire video sequence; when 0 use_ref_frame_mvs will also always be 0. This field corresponds to the syntax element of the same name from the AV1 specification (from the sequence header).

### -field coding.reference_frame_update

Indicates that the reference frame update process as specified by section 7.20 of the AV1 specification should be performed after decoding this frame. Otherwise section 7.21 should be performed.

### -field coding.Reserved

Reserved bit fields to complete the packed structure. Shall be set to 0. The accelerator shall ignore the values in the reserved bit fields.

### -field coding.CodingParamToolFlags

Provides an alternative way to access the bit fields related to coding tool flags.

### -field format

Contains format and picture information.

### -field format.frame_type

The frame type of the current frame. This field corresponds to the syntax element of the same name in the AV1 specification and affects the decoding process accordingly. The allowed values are 0, 1, 2 or 3, for the four types of AV1 frames: KEY_FRAME, INTER_FRAME, INTRA_ONLY_FRAME, and S_FRAME.

### -field format.show_frame

Indicates whether the current frame is intended to be output and displayed after its decoding is completed. This field corresponds to the syntax element of the same name in the AV1 specification and affects the decoding process accordingly. In DXVA, this has no direct effect, as the host controls the display of decoded frames separately by other function calls.

### -field format.showable_frame

When equal to 1, specifies that the frame can be output using the show_existing_frame mechanism; otherwise equal to zero, which specifies that this frame will not be output using the show_existing_frame mechanism.

### -field format.subsampling_x

Together with **subsampling_y**, indicates the chroma sampling format. See Remarks.

### -field format.subsampling_y

Together with **subsampling_x**, indicates the chroma sampling format. See Remarks.

### -field format.mono_chrome

Indicates whether the bitstream is monochrome. If 1 then only a luma plane is present. This field corresponds to the syntax element of the same name from the Color Config Syntax of the AV1 specification. The allowed values are restricted by the profile value.

### -field format.Reserved

Reserved bit fields to complete the packed structure. Shall be set to 0. The accelerator shall ignore the values in the reserved bit fields.

### -field format.FormatAndPictureInfoFlags

Provides an alternative way to access the bit fields related to format and picture info.

### -field primary_ref_frame

Specifies which reference frame contains the CDF values and other state that should be loaded at the start of the frame. This field is 0x7 when there is no primary reference frame. It corresponds to the syntax element of the same name from the AV1 specification.

### -field order_hint

The output ordering of the current frame. Corresponds to OrderHint from the AV1 specification.

### -field order_hint_bits

Corresponds to the syntax element named order_hint_bits_minus_1 in the AV1 specification. This field is defined as: order_hint_bits_minus_1 + 1. This field will be 0 when enable_order_hint from the AV1 specification is 0.

When this value is 0, no tools based on OrderHint should be used and the value of order_hint is undefined. When non-zero, it affects the calculation of relative distance accordingly (see function get_relative_dist from the AV1 specification).

### -field frame_refs

### -field RefFrameMapTextureIndex

Array of uncompressed frame buffer surfaces. Entries that will not be used for decoding the current picture, or any subsequent pictures, are indicated by setting this value to 0xFF. If the value is not 0xFF, the entry may be used as a reference surface for decoding the current picture or a subsequent picture in decoding order.

All uncompressed surfaces that correspond to frames that may be used for reference in the decoding process of the current picture or any subsequent picture shall be present in the **RefFrameMapTextureIndex** array (regardless of whether these pictures are actually used in the decoding process of the current frame). No particular order is specified for the ordering of the entries in the **RefFrameMapTextureIndex** array.

> [!NOTE]
> The accelerator must use the content of the **RefFrameMapTextureIndex** as provided by the accelerator rather than trying to derive this information from the bitstream (in order to ensure stateless operation for which the decoded frame buffer handling is to be performed under the control of the host rather than inferred from the bitstream by the accelerator).

### -field loop_filter

Structure with loop filter parameters.

### -field loop_filter.filter_level

An array containing loop filter strength values. Corresponds to the syntax element of the same name in the AV1 specification, and affects the decoding processes of the deblocking filter accordingly. See **sharpness_level** field for more information.

### -field loop_filter.filter_level_u

### -field loop_filter.filter_level_v

### -field loop_filter.sharpness_level

Indicates the sharpness level. The **filter_level** and **sharpness_level** values together determine when a block edge is filtered, and by how much the filtering can change the sample values. The loop filter process is described in section 7.14 of the AV1 specification.

### -field loop_filter.DUMMYUNIONNAME

### -field loop_filter.DUMMYUNIONNAME.mode_ref_delta_enabled

When equal to 1, indicates that the filter level depends on the mode and reference frame used to predict a block. This field corresponds to the syntax element named loop_filter_delta_enabled from the AV1 specification.

### -field loop_filter.DUMMYUNIONNAME.mode_ref_delta_update

When equal to 1, indicates that additional syntax elements are present that specify which mode and reference frame deltas are to be updated. This field corresponds to the syntax element named loop_filter_delta_update from the AV1 specification.

### -field loop_filter.DUMMYUNIONNAME.delta_lf_multi

When equal to 1, indicates that separate loop filter deltas are sent for horizontal luma edges, vertical luma edges, U edges and V edges. This field corresponds to the syntax element named delta_lf_multi from the AV1 specification.

### -field loop_filter.DUMMYUNIONNAME.delta_lf_present

When equal to 1, indicates that loop filter deltas are present. This is needed for the loop filter decoding process: read_delta_lf(). This field corresponds to the syntax element named delta_lf_present from the AV1 specification.

### -field loop_filter.DUMMYUNIONNAME.Reserved

Reserved bit fields to complete the packed structure. Shall be set to 0. The accelerator shall ignore the values in the reserved bit fields.

### -field loop_filter.DUMMYUNIONNAME.ControlFlags

Provides an alternative way to access the bit fields related to loop filter flags.

### -field loop_filter.ref_deltas

Corresponds to the syntax element named loop_filter_ref_deltas in the AV1 specification and affects the decoding processes of the loop filter accordingly.

### -field loop_filter.mode_deltas

Corresponds to the syntax element named loop_filter_mode_deltas in the AV1 specification and affects the decoding process of the loop filter accordingly.

### -field loop_filter.delta_lf_res

The left shift which should be applied to the decoded loop filter delta values. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field loop_filter.frame_restoration_type

The loop restoration mode for this frame. This field corresponds to the FrameRestorationType syntax element from the AV1 specification. It can be one of the following, which are the same values as specified in the AV1 specification:

| FrameRestorationType | Name of FrameRestorationType |
| -------------------- | ---------------------------- |
| 0                    | RESTORE_NONE                 |
| 1                    | RESTORE_WIENER               |
| 2                    | RESTORE_SGRPROJ              |
| 3                    | RESTORE_SWITCHABLE           |

### -field loop_filter.log2_restoration_unit_size

The log2 size of loop restoration units in units of samples in the current plane. Element 0 corresponds to the luma plane, element 1 to the U plane and element 2 to the V plane. This field corresponds to the log2(LoopRestorationSize[plane]) variable from the AV1 specification.

### -field loop_filter.Reserved16Bits

Reserved bit fields to complete the packed structure. Shall be set to 0. The accelerator shall ignore the values in the reserved bit fields.

### -field quantization

Contains quantization information.

### -field quantization.DUMMYUNIONNAME

### -field quantization.DUMMYUNIONNAME.delta_q_present

Specifies whether the quantizer index delta values are present. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field quantization.DUMMYUNIONNAME.delta_q_res

The left shift, which should be applied to decoded quantizer index delta values. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field quantization.DUMMYUNIONNAME.Reserved

Reserved bit fields to complete the packed structure. Shall be set to 0. The accelerator shall ignore the values in the reserved bit fields.

### -field quantization.DUMMYUNIONNAME.ControlFlags

Provides an alternative way to access the bit fields related to quantization.

### -field quantization.base_qindex

Indicates the base frame qindex. This field corresponds to the syntax element named base_q_idx from the AV1 specification.

### -field quantization.y_dc_delta_q

The Y DC quantizer relative to base_qindex. This field corresponds to DeltaQYDc from the AV1 specification.

### -field quantization.u_dc_delta_q

The U DC quantizer relative to base_qindex. This field corresponds to DeltaQUDc from the AV1 specification.

### -field quantization.v_dc_delta_q

The V DC quantizer relative to base_qindex. This field corresponds to DeltaQVDc from the AV1 specification.

### -field quantization.u_ac_delta_q

The U AC quantizer relative to base_qindex. This field corresponds to DeltaQUAc from the AV1 specification.

### -field quantization.v_ac_delta_q

The V AC quantizer relative to base_qindex. This field corresponds to DeltaQVAc from the AV1 specification.

### -field quantization.qm_y

The level in the quantizer matrix that should be used for luma plane decoding. When unspecified (using_qmatrix=0), this field will be 0xFF (which is an invalid quantizer matrix level). This field corresponds to the syntax element of the same name from the AV1 specification.

### -field quantization.qm_u

The level in the quantizer matrix that should be used for U-plane decoding. When unspecified (using_qmatrix=0), this field will be 0xFF (which is an invalid quantizer matrix level). This field corresponds to the syntax element of the same name from the AV1 specification.

### -field quantization.qm_v

The level in the quantizer matrix that should be used for V-plane decoding. When unspecified (using_qmatrix=0), this field will be 0xFF (which is an invalid quantizer matrix level). This field corresponds to the syntax element of the same name from the AV1 specification.

### -field quantization.Reserved16Bits

Reserved.

### -field cdef

Constrained directional enhancement filter (CDEF) parameters.

### -field cdef.DUMMYUNIONNAME

### -field cdef.DUMMYUNIONNAME.damping

Controls the amount of damping in the deringing filter. This field corresponds to the variable named cdef_damping_minus_3 from the AV1 specification.

### -field cdef.DUMMYUNIONNAME.bits

The number of bits used to signal the CDEF filter setting. This field corresponds to the syntax element named cdef_bits from the AV1 specification.

### -field cdef.DUMMYUNIONNAME.Reserved

Reserved bit fields to complete the packed structure. Shall be set to 0. The accelerator shall ignore the values in the reserved bit fields.

### -field cdef.DUMMYUNIONNAME.ControlFlags

Provides an alternative way to access the bit fields related to CDEF parameters.

### -field cdef.primary

Primary filter strength for the y-channel. This field corresponds to cdef_y_pri_strength from the AV1 specification.

### -field cdef.secondary

Secondary filter strength for the y-channel. This field corresponds to cdef_y_sec_strength from the AV1 specification.

### -field cdef.combined

Provides an alternative way to access the y_strengths primary and secondary bits.

### -field cdef.y_strengths

The primary and secondary filter strengths for the y-channel.

### -field cdef.uv_strengths

The primary and secondary filter strengths for the uv-channels.  This corresponds to the cdef_uv_pri_strength, and cdef_uv_sec_strength syntax elements from the AV1 specification.  

### -field interp_filter

Corresponds to the same syntax element of the same name in the AV1 specification and affects the decoding process of motion compensation interpolation accordingly. The table below shows the possible values of interp_filter.

| Value | Filter type  |
| ----- | -----------  |
| 0     | normal 8-tap |
| 1     | smooth 8-tap |
| 2     | sharp 8-tap  |
| 3     | bilinear     |
| 4     | all filters  |

### -field segmentation

Segmentation parameters.

### -field segmentation.DUMMYUNIONNAME

### -field segmentation.DUMMYUNIONNAME.enabled

When equal to 1, indicates that this frame makes use of the segmentation tool. This field corresponds to the syntax element named segmentation_enabled from the AV1 specification.

### -field segmentation.DUMMYUNIONNAME.update_map

When equal to 1, indicates that the segmentation map is updated during the decoding of this frame. This field corresponds to the syntax element named segmentation_update_map from the AV1 specification.

### -field segmentation.DUMMYUNIONNAME.update_data

When equal to 1, indicates that new parameters are supplied for each segment. This field corresponds to the syntax element named segmentation_update_data from the AV1 specification.

### -field segmentation.DUMMYUNIONNAME.temporal_update

When equal to 1, indicates that the updates to the segmentation map are coded relative to the existing segmentation map. This field corresponds to the syntax element named segmentation_temporal_update from the AV1 specification.

### -field segmentation.DUMMYUNIONNAME.Reserved

Reserved bit fields to complete the packed structure. Shall be set to 0. The accelerator shall ignore the values in the reserved bit fields.

### -field segmentation.DUMMYUNIONNAME.ControlFlags

Provides an alternative way to access the bit fields related to segmentation.

### -field segmentation.Reserved24Bits

Reserved.

### -field segmentation.alt_q

### -field segmentation.alt_lf_y_v

### -field segmentation.alt_lf_y_h

### -field segmentation.alt_lf_u

### -field segmentation.alt_lf_v

### -field segmentation.ref_frame

### -field segmentation.skip

### -field segmentation.globalmv

### -field segmentation.mask

### -field segmentation.feature_mask

Specifies which segment data features are updated in this frame. This field corresponds to the syntax element feature_enabled from the AV1 specification.

### -field segmentation.feature_data

Specifies segmentation feature values. This field corresponds to the syntax element feature_value from the AV1 specification.

### -field film_grain

Film grain parameters.

### -field film_grain.DUMMYUNIONNAME

### -field film_grain.DUMMYUNIONNAME.apply_grain

When equal to 1, indicates that film grain should be added to this frame. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field film_grain.DUMMYUNIONNAME.scaling_shift_minus8

The shift -8 applied to values of the chroma component. This field corresponds to the syntax element named grain_scaling_minus8 from the AV1 specification.

### -field film_grain.DUMMYUNIONNAME.chroma_scaling_from_luma

When equal to 1, specifies that the chroma scaling is inferred from the luma scaling. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field film_grain.DUMMYUNIONNAME.ar_coeff_lag

The number of auto-regressive coefficients for luma and chroma. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field film_grain.DUMMYUNIONNAME.ar_coeff_shift_minus6

The range of auto-regressive coefficients. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field film_grain.DUMMYUNIONNAME.grain_scale_shift

Specifies how much the Gaussian random numbers should be scaled down during the grain synthesis process. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field film_grain.DUMMYUNIONNAME.overlap_flag

When equal to 1, indicates that the overlap between film grain blocks shall be applied. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field film_grain.DUMMYUNIONNAME.clip_to_restricted_range

If equal to 1, indicates that clipping to the restricted (studio) range shall be applied to the sample
values after adding the film grain (see the semantics for color_range for an explanation of studio swing).
If equal to 0, indicates that clipping to the full range shall be applied to the sample values after
adding the film grain.

### -field film_grain.DUMMYUNIONNAME.matrix_coeff_is_identity

### -field film_grain.DUMMYUNIONNAME.Reserved

Reserved bit fields to complete the packed structure. Shall be set to 0. The accelerator shall ignore the values in the reserved bit fields.

### -field film_grain.DUMMYUNIONNAME.ControlFlags

Provides an alternative way to access the bit fields related to film grain.

### -field film_grain.grain_seed

The starting value for the pseudo-random number generator used for film grain synthesis. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field film_grain.scaling_points_y

Represents the x,y coordinates for the piecewise linear scaling function for the y-plane. This is a 2D array, at each piecewise segment the first value specified is the x (luma value) coordinate and the second value is the scaling value (y, output). This field corresponds to the point_y_value syntax element from the AV1 specification.

### -field film_grain.num_y_points

The number of valid piecewise segments specified in scaling_points_y. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field film_grain.scaling_points_cb

Represents the x,y coordinates for the piecewise linear scaling function for the cb-plane. This is a 2D array, at each piecewise segment the first value specified is the x (luma value) coordinate and the second value is the scaling value (y, output). This field corresponds to the point_cb_value syntax element from the AV1 specification.

### -field film_grain.num_cb_points

The number of valid piecewise segments specified in scaling_points_cb. This field corresponds to the syntax elements of the same name from the AV1 specification.

### -field film_grain.scaling_points_cr

Represents the x,y coordinates for the piecewise linear scaling function for the cr-plane. This is a 2D array, at each piecewise segment the first value specified is the x (luma value) coordinate and the second value is the scaling value (y, output). This field corresponds to the point_cr_value syntax element from the AV1 specification.

### -field film_grain.num_cr_points

The number of valid piecewise segments specified in scaling_points_cr. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field film_grain.ar_coeffs_y

The auto-regressive coefficients for the Y plane. This field corresponds to the ar_coeffs_y_plus_128 syntax element from the AV1 specification.

### -field film_grain.ar_coeffs_cb

The auto-regressive coefficients for the U plane. This field corresponds to the ar_coeffs_cb_plus_128 syntax element from the AV1 specification.

### -field film_grain.ar_coeffs_cr

The auto-regressive coefficients for the V plane. This field corresponds to the ar_coeffs_cr_plus_128 syntax element from the AV1 specification.

### -field film_grain.cb_mult

The multiplier for the Cb component used in derivation of the input index to the component scaling function. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field film_grain.cb_luma_mult

The multiplier used for the luma component into the Cb component scaling function. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field film_grain.cr_mult

The multiplier for the Cr component used in derivation of the input index to the component scaling function. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field film_grain.cr_luma_mult

The multiplier used for the luma component into the Cr component scaling function. This field corresponds to the syntax elements of the same name from the AV1 specification.

### -field film_grain.Reserved8Bits

Reserved.

### -field film_grain.cb_offset

The offset used in derivation of the input index to the Cb component scaling function. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field film_grain.cr_offset

The offset used in derivation of the input index to the Cr component scaling function. This field corresponds to the syntax element of the same name from the AV1 specification.

### -field Reserved32Bits

Reserved.

### -field StatusReportFeedbackNumber

Arbitrary number set by the host decoder to use as a tag in the status report feedback data. The value should not be equal to 0, and should be different in each call to Execute. For more information, see the Status Report Data Structure section in the [Direct X Video Acceleration Specification for AV1 Video Coding](https://www.microsoft.com/download/details.aspx?id=101577).

## -remarks

If **width** and **height** are derived for the frame (for example via the frame_size_override_flag), the host decoder will derive the appropriate values and store the result in these fields. If **superres** is enabled, these values represent the post-scaled frame resolution (referred to in the AV1 specification as UpscaledWidth).

The allowed values of **subsampling_x** and **subsampling_y** are constrained by the profile value. The following table specifies the allowed values for **subsampling_x** and **subsampling_y**, and the associated chroma formats.

| subsampling_x | subsampling_y | Chroma format |
| ------------- | ------------- | ------------- |
| 1             | 1             | 4:2:0         |
| 1             | 0             | 4:2:2         |
| 0             | 0             | 4:4:4         |

See the [Direct X Video Acceleration Specification for AV1 Video Coding](https://www.microsoft.com/download/details.aspx?id=101577) for detailed information, including how to use this structure.
