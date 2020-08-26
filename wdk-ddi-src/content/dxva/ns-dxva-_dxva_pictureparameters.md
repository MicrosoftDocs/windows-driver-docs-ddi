---
UID: NS:dxva._DXVA_PictureParameters
title: _DXVA_PictureParameters (dxva.h)
description: The DXVA_PictureParameters structure is sent by the host decoder to the accelerator to provide the picture-level parameters of a compressed picture for decoding on the accelerator.
old-location: display\dxva_pictureparameters.htm
tech.root: display
ms.assetid: e54c1d6a-b0bb-4754-9399-5f3b1b9b2534
ms.date: 05/10/2018
keywords: ["DXVA_PictureParameters structure"]
ms.keywords: "*LPDXVA_PictureParameters, DXVA_PictureParameters, DXVA_PictureParameters structure [Display Devices], LPDXVA_PictureParameters, LPDXVA_PictureParameters structure pointer [Display Devices], _DXVA_PictureParameters, display.dxva_pictureparameters, dxva/DXVA_PictureParameters, dxva/LPDXVA_PictureParameters, dxvaref_10ab1c20-a070-42ad-95da-0d8a20d19228.xml"
f1_keywords:
 - "dxva/DXVA_PictureParameters"
 - "DXVA_PictureParameters"
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dxva.h
api_name:
- DXVA_PictureParameters
targetos: Windows
req.typenames: DXVA_PictureParameters, *LPDXVA_PictureParameters
---

# _DXVA_PictureParameters structure


## -description


The DXVA_PictureParameters structure is sent by the host decoder to the accelerator to provide the picture-level parameters of a compressed picture for decoding on the accelerator.


## -struct-fields

### -field wDecodedPictureIndex

Specifies the destination frame buffer for the decoded macroblocks.


### -field wDeblockedPictureIndex

Specifies the destination frame buffer for the deblocked output picture when <b>bPicDeblocked</b> is 1. This member has no meaning and must be zero if <b>bPicDeblocked</b> is zero. This member may be the same as <b>wDecodedPictureIndex</b>.


### -field wForwardRefPictureIndex

Specifies the frame buffer index of the picture to be used as a reference picture for forward prediction of the current picture. Must not be the same as <b>wDecodedPictureIndex</b>. This member must be 0xFFFF if <b>bPicIntra</b> is 1.


### -field wBackwardRefPictureIndex

Specifies the frame buffer index of the picture to be used as a reference picture for backward prediction of the current picture. This member must not be the same as <b>wDecodedPictureIndex</b> if backward reference motion prediction is used. This member must be 0xFFFF if <b>bPicBackwardPrediction</b> is zero.


### -field wPicWidthInMBminus1

Specifies the width of the current picture in units of macroblocks, minus 1. The width of the picture in macroblocks is derived by adding 1 to <b>wPicWidthInMBminus1</b>.


### -field wPicHeightInMBminus1

Specifies the height of the current picture in units of macroblocks, minus 1. The height of the picture in macroblocks is derived by adding 1 to <b>wPicHeightInMBminus1</b>.


### -field bMacroblockWidthMinus1

Specifies the destination luminance sample width of a macroblock, minus 1. This is equal to 15 for MPEG-1, MPEG-2, H.263, and MPEG-4.


### -field bMacroblockHeightMinus1

Specifies the destination luminance sample height of a macroblock, minus 1. This is equal to 15 for MPEG-1, MPEG-2, H.261, H.263, and MPEG-4.


### -field bBlockWidthMinus1

Specifies the block width of a residual difference block minus 1. This is equal to 7 for MPEG-1, MPEG-2, H.261, H.263, and MPEG-4. This is 7 if the <b>bConfig4GroupedCoefs</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a> structure is 1. Residual difference blocks within a macroblock are sent in the order specified as in MPEG-2 Figures 6-10, 6-11, and 6-12 (raster-scan order for Y, followed by all 4:2:0 blocks of Cb in raster-scan order, followed by 4:2:0 blocks of Cr, followed by 4:2:2 blocks of Cb, followed by 4:2:2 blocks of Cr, followed by 4:4:4 blocks of Cb, followed by 4:4:4 blocks of Cr). A derived term called <i>W</i><sub>T</sub> is formed by adding 1 to <b>bBlockWidthMinus1</b>.


### -field bBlockHeightMinus1

Specifies the block height of a residual difference block, minus 1. This is equal to 7 for MPEG-1, MPEG-2, H.261, H.263, and MPEG-4. This is 7 if <b>bConfig4GroupedCoefs</b> is 1. A derived term called <i>H</i><sub>T</sub> is formed by adding 1 to <b>bBlockHeightMinus1</b>.


### -field bBPPminus1

Specifies the number of bits per pixel for the video sample values, minus 1. This is at least 7 (indicating 8-bit pixels). This is equal to 7 for MPEG-1, MPEG-2, H.261, and H.263. A larger number of bits per pixel is supported in some operational modes of MPEG-4. A derived term called <i>BPP</i> is formed by adding 1 to <b>bBPPminus1</b>.


### -field bPicStructure

Indicates whether the current picture is a top-field picture (a value 1), a bottom-field picture (a value 2), or a frame picture (a value 3). In progressive-scan frame-structured coding such as in H.261, <b>bPicStructure</b> is 3. A derived value <i>PicCurrentField</i> is defined as zero unless <b>bPicStructure</b> is 2 (bottom field). In which case, it is 1. This member has the same meaning as the <i>picture_structure </i>variable defined in Section 6.3.10 and Table 6-14 of <a href="https://docs.microsoft.com/windows-hardware/drivers/display/mpeg-2--h-262-">MPEG-2 (H.262)</a>.


### -field bSecondField

Indicates whether, in the case of field-structured coding (when <b>bPicStructure</b> is 1 or 2), the current field is the second field of a picture. This is used to determine whether the opposite-parity field used as a reference for the opposite-parity lines for motion compensation prediction is the opposite-parity field of the reference picture or the opposite-parity field of the current picture. If <b>bSecondField</b> is 1, the current field is the second field of a picture and the field used as a reference for the opposite-parity lines for motion compensation are the opposite-parity lines of the current picture. (In both cases, the field used as a reference for the same-parity lines for motion compensation are the same-parity lines of the reference picture.) Otherwise, <b>bSecondField</b> is zero.


### -field bPicIntra

Indicates whether motion-compensated prediction is needed for this picture. If <b>bPicIntra</b> is 1, all macroblocks are sent with either the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_i_offhostidct_1">DXVA_MBctrl_I_OffHostIDCT_1</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_i_hostresiddiff_1">DXVA_MBctrl_I_HostResidDiff_1</a> macroblock control command structure, in which the <i>IntraMacroblock</i> flag is equal to 1 . That is, no motion-compensated prediction is performed for the picture. Otherwise, some macroblocks of the picture may have the <i>IntraMacroblock</i> parameter of the macroblock control command equal to zero, and the macroblock control command structure will use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_p_hostresiddiff_1">DXVA_MBctrl_P_HostResidDiff_1</a> structure or the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_p_offhostidct_1">DXVA_MBctrl_P_OffHostIDCT_1</a> structure.


### -field bPicBackwardPrediction

Indicates whether any macroblocks of the current picture might include backward prediction. If <b>bPicIntra</b> is 1, <b>bPicBackwardPrediction</b> must be zero. If <b>bPicBackwardPrediction</b> is zero, <i>MotionBackward</i> must be zero in all macroblock control commands of the picture (within each DXVA_MBctrl_I_HostResidDiff_1, DXVA_MBctrl_I_OffHostIDCT_1, DXVA_MBctrl_P_HostResidDiff_1, or DXVA_MBctrl_P_OffHostIDCT_1 structure). If <b>bPicBackwardPrediction</b> is 1, some macroblocks of the picture may have <i>MotionBackward</i> equal to 1.


### -field bBidirectionalAveragingMode

Indicates the rounding method for combining prediction planes in bidirectional motion compensation (used for B pictures and dual-prime motion). The value zero indicates MPEG-1 and MPEG-2 rounded averaging (in which values halfway between two integers are rounded upward to the next higher integer), and the value 1 indicates H.263 truncated averaging (in which values halfway between two integers are rounded downward to the next lower integer). <b>bBidirectionalAveragingMode</b> must be zero if no bidirectional averaging is needed.


### -field bMVprecisionAndChromaRelation

This member indicates the precision of luminance motion vectors and how chrominance motion vectors are derived from luminance motion vectors.

The following table lists values for this member with the specified luminance motion vector precision and a description of how the chrominance motion vectors are derived.

| **Value** | **Description** | 
|:--|:--|
| 0 | Luminance motion vectors have half-sample precision. Chrominance motion vectors are derived from luminance motion vectors in accordance with [MPEG-2 (H.262)](https://docs.microsoft.com/windows-hardware/drivers/display/mpeg-2--h-262-) . | 
| 1 | Luminance motion vectors have half-sample precision. Chrominance motion vectors are derived from luminance motion vectors in accordance with [H.263](https://docs.microsoft.com/windows-hardware/drivers/display/itu-t-h-263) . | 
| 2 | Luminance motion vectors have full-sample precision. Chrominance motion vectors are derived from luminance motion vectors in accordance with [H.261](https://docs.microsoft.com/windows-hardware/drivers/display/itu-t-h-261)  (dividing by two and truncating toward zero to full-sample values). | 
| 3 | Reserved. | 

### -field bChromaFormat

Affects the number of prediction error blocks expected by the accelerator. This variable is defined in MPEG-2 (H.262). For <a href="https://docs.microsoft.com/windows-hardware/drivers/display/mpeg-1">MPEG-1</a>, MPEG-2 Main Profile, H.261 and H.263 bitstreams, this value must always be set to 1, indicating 4:2:0 format. If a value of 2, this indicates 4:2:2, and if a value of 3, indicates 4:4:4 sampling. This member must be equal to 1 if the <b>bConfig4GroupedCoefs</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a> is 1 (because <b>bConfig4GroupedCoefs</b> operation does not include the EOB indication needed within coefficient data in 4:2:2 and 4:4:4 formats).

> [!NOTE]
> Horizontal chroma siting differs slightly among H.261, H.263, and MPEG-1 versus MPEG-2 and MPEG-4. This difference is assumed to be small enough to ignore.

### -field bPicScanFixed

When using accelerator-based IDCT processing of residual difference blocks, a value of 1 for this flag indicates that the inverse-scan method is the same for all macroblocks in the picture. A value of zero indicates that it is not. This member must be 1 if the <b>bConfigHostInverseScan</b> member is 1 or if the <b>bConfigResidDiffAccelerator</b> member is zero in DXVA_ConfigPictureDecode.

### -field bPicScanMethod

Indicates the fixed inverse scan method for the picture when <b>bPicScanFixed</b> is 1. When <b>bPicScanFixed</b> is zero, this member has no meaning and must have a value of zero.

If the <b>bConfigHostInverseScan</b> member of DXVA_ConfigPictureDecode is zero, the scan method defined by this member can be one of the following.

|bPicScanMethod|Scan Method|
|--- |--- |
|0|Zigzag scan (MPEG-2)|
|1|Alternate-vertical scan (MPEG-2)|
|2|Alternate-horizontal scan (H.263)|
 
If the <b>bConfigHostInverseScan</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a> is 1, the scan method defined by <b>bPicScanMethod</b> must be set as follows.

|bPicScanMethod|Scan Method|
|--- |--- |
|3|Arbitrary scan with absolute coefficient address.|

### -field bPicReadbackRequests

Indicates whether read-back control requests are issued for the current picture. A value of 1 indicates that read-back requests are present, and a value of zero indicates that they are not. Read-back requests indicate that values of macroblocks are read back in the final decoded and deblocked picture (if deblocking is applied with <b>wDeblockedPictureIndex</b> equal to <b>wDecodedPictureIndex</b>). 


### -field bRcontrol

Defines the rounding method to be used for half-sample motion compensation. This variable is defined in H.263 Section 6.1.2. A value of zero indicates the half-sample rounding method found in MPEG-1, MPEG-2, and the first version of H.263. A value of 1 indicates the rounding method that includes a downward averaging bias that can be selected in some optional modes of H.263 and MPEG-4. It is meaningless for H.261, because H.261 has no half-sample motion compensation. It must be set to zero for all MPEG-1 and MPEG-2 bitstreams in order to conform with the rounding operator defined by those standards.


### -field bPicSpatialResid8

Indicates how spatial-domain difference blocks are sent to the accelerator from the host. A value of 1 indicates that spatial-domain difference blocks for host-based residual difference decoding can be sent using 8-bit samples, and a value of zero indicates that they cannot. 

This member must be zero if the <b>bConfigResidDiffHost</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a> is zero or if <i>BPP</i> is greater than 8. This member must be 1 if <i>BPP</i> is 8, <b>bPicIntra</b> is 1 and <b>bConfigResidDiffHost</b> is 1. This member must be 1 if the <b>bConfigSpatialResid8</b> member of DXVA_ConfigPictureDecode is 1. 

If this member is equal to 1, spatial-domain intra macroblocks are sent as 8-bit values (that are either signed or unsigned, as determined by the <b>bConfigIntraResidUnsigned</b> member of DXVA_ConfigPictureDecode), and spatial-domain nonintra macroblock differences are sent as signed 8-bit difference values relative to some motion-compensated prediction.

The <b>bPicSpatialResid8</b> member differs from the <b>bConfigSpatialResid8</b> member of DXVA_ConfigPictureDecode in that it is an indication for a particular picture, not a global indication for the entire video sequence. In some cases such as in an <a href="https://docs.microsoft.com/windows-hardware/drivers/">intra picture</a> with <i>BPP</i> equal to 8, <b>bPicSpatialResid8</b> will be 1 even though <b>bConfigSpatialResid8</b> may be zero.

### -field bPicOverflowBlocks

Indicates whether spatial-domain difference blocks are sent to the accelerator from the host using overflow blocks. A value of 1 indicates that spatial-domain difference blocks for host-based residual difference decoding of a picture may be sent using overflow blocks. A value of zero indicates that spatial-domain difference blocks are not sent using overflow blocks. This member must be zero if <b>bConfigResidDiffHost</b> is zero or if <b>bConfigSpatialResid8</b> is zero, or if <i>BPP</i> is greater than 8. Parameters <b>bConfigResidDiffHost</b> and <b>bConfigSpatialResid8</b> are members of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a>. <b>bPicOverflowBlocks</b> indicates whether any overflow blocks may be present for the particular picture. In an intra picture with <i>BPP</i> equal to 8, <b>bPicOverflowBlocks</b> must be zero as no overflow blocks are needed in this case.

### -field bPicExtrapolation

Indicates whether motion vectors over picture boundaries are allowed as specified by H.263 Annex D and MPEG-4. This requires either allocation of picture planes that are two macroblocks wider (one extra macroblock at the left and another at the right) and two macroblocks taller (one extra macroblock at the top and another at the bottom) than the decoded picture size, or clipping of the address of each individual pixel access to within the picture boundaries. Macroblock addresses in this specification are for macroblocks in the interior of the picture, not including padding.

### -field bPicDeblocked

Indicates whether deblocking commands are sent for this picture to create a deblocked output picture. The deblocked output picture is placed in the picture buffer indicated by <b>wDeblockedPictureIndex</b>. If <b>bPicDeblocked</b> is 1, deblocking commands are sent and the deblocked frame is generated. If <b>bPicDeblocked</b> is zero, no deblocking commands are sent and no deblocked picture is generated.


### -field bPicDeblockConfined

Indicates whether deblocking filter command buffers confine the effect of deblocking filter operations to the set of macroblocks contained in the deblocking filter command buffer. 


### -field bPic4MVallowed

Specifies whether four forward-reference motion vectors per macroblock are allowed as used in H.263 Annexes F and J.


### -field bPicOBMC

Specifies whether motion compensation for the current picture operates using overlapped block motion compensation (OBMC) as specified in H.263 Annex F. Must be zero if <b>bPic4MVallowed</b> is zero.


### -field bPicBinPB

Specifies whether bidirectionally predicted macroblocks in the picture use B-picture in PB-frame motion compensation. This restricts the bidirectionally predicted area for each macroblock to the region of the corresponding macroblock in the backward reference picture, as specified in Annexes G and M of H.263.


### -field bMV_RPS

Specifies the use of motion vector reference picture selection. If <b>bMV_RPS</b> is 1, this indicates that a reference picture index is sent for each motion vector rather than just forward and possibly backward motion picture indexes for the picture as a whole. If <b>bMV_RPS</b> is 1, the <b>wForwardRefPictureIndex</b> and <b>wBackwardRefPictureIndex</b> members have no meaning and must be zero.


### -field bReservedBits

This is reserved for packing and alignment. Must be zero.


### -field wBitstreamFcodes

Indicates the motion vector <i>f_code</i> values as defined in MPEG-2 for raw bitstream processing. Each <i>f_code</i> value takes 4 bits. These values are packed into a 16-bit word as follows.

|Bits|Description|
|--- |--- |
|12 through 15 (the most significant bits)|f_code[0][0]: The forward horizontal f_code|
|8 through 11|f_code[0][1]: The forward vertical f_code|
|4 through 7|f_code[1][0]: The backward horizontal f_code|
|0 through 3 (the least significant bits)|f_code[1][1]: The backward vertical f_code|

When the <b>bConfigBitstreamRaw</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a> structure is 1, <b>wBitstreamFcodes</b> contains four motion vector <i>f_code</i> values. If <b>bConfigBitstreamRaw</b> is 1 and any of the four <i>f_code</i> values is unnecessary or irrelevant due to the structure of the bitstream data or due to the <i>f_code</i> value not being needed in the relevant video coding bitstream syntax (such as in H.261 or H.263), then each irrelevant f_code value is 0xF.

If the <b>bConfigBitstreamRaw</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a> structure is zero, then <b>wBitstreamFcodes</b> is set to 0xFFFF (all f_code values are set to 0xF).

> [!NOTE]
> MPEG-1 bitstreams provide this information in a different form. Therefore for MPEG-1 bitstreams, f_code[0][0] and f_code[0][1] are equal to MPEG-1's forward_f_code, and f_code[1][0] and f_code[1][1] are equal to MPEG-1's backward_f_code.

### -field wBitstreamPCEelements

When the <b>bConfigBitstreamRaw</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a> is 1, this member contains a set of flags necessary for the bitstream decoding process of MPEG-2 video. It is not used and must be zero when <b>bConfigBitstreamRaw</b> is zero and for non-MPEG-2 video. The bits in this member are defined by their correspondence with bitstream elements of the MPEG-2 picture coding extension as follows.

|Bits|Description|
|--- |--- |
|14 and 15|IntraDCprecision is equal to intra_dc_precision.|
|12 and 13|AnotherPicStructure is equal to picture_structure. This must be equal to the bPicStructure member of this structure.|
|11|TopFieldFirst is equal to top_field_first.|
|10|FrameDCTprediction is equal to frame_pred_frame_dct.|
|9|ConcealmentMVs is equal to concealment_motion_vectors.|
|8|QuantScaleType is equal to q_scale_type.|
|7|IntraVLCformat is equal to intra_vlc_format.|
|6|AlternateScan is equal to alternate_scan.|
|5|RepeatFirstField is equal to repeat_first_field (not needed by the accelerator).|
|4|Chroma420type is equal to chroma_420_type (not needed by the accelerator and restricted by MPEG-2 to be equal to progressive_frame).|
|3|ProgressiveFrame is equal to progressive_frame.|
|0, 1, and 2|Reserved Bits. These are the least significant bits.|

### -field bBitstreamConcealmentNeed

Indicates the likelihood of errors in the bitstream data when the <b>bConfigBitstreamRaw</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a> structure is 1. Must be zero if <b>bConfigBitstreamRaw</b> is zero.

Video accelerators must be designed not to fail or lock up, regardless of the content of the data given to them. Therefore, it may be helpful for a video accelerator to have information about the host's assessment of the likelihood of syntactical errors. This is in order to determine whether there is a need to invoke a more complex error concealment algorithm that might slow down the bitstream decoding process. Allowed values for this member are as follows (all other values are reserved).

|Value|Meaning|
|--- |--- |
|0|The bitstream is unlikely to contain any significant amount of errors in its syntactical format.|
|1|The bitstream may contain some errors. These errors are likely to be infrequent (for example, an error once or twice per hour).|
|2|The bitstream is likely to contain some errors. These errors are likely to occur with a frequency that could impact the user experience (for example, an error every five to ten minutes).|
|3|The bitstream is likely to contain relatively significant, serious, and frequent syntactical format errors (for example, one or more errors per minute).|
 
### -field bBitstreamConcealmentMethod

Specifies a preferred default method for error concealment processing when the <b>bConfigBitstreamRaw</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a> structure is 1. Must be zero if <b>bConfigBitstreamRaw</b> is zero. Allowed values for this member are as follows (all other values are reserved).

| **Value** | **Error Concealment Method** | 
|:--|:--|
| 0 | Unknown or unspecified. | 
| 1 | Spatial intra-picture concealment within the picture. | 
| 2 | Forward-motion reference picture for inter-picture concealment (to be used more typically in a [P picture](https://docs.microsoft.com/windows-hardware/drivers/)  or in a [B picture](https://docs.microsoft.com/windows-hardware/drivers/)  that is closer to its forward-motion reference picture than to its backward-motion reference picture). | 
| 3 | Backward-motion reference picture for inter-picture concealment (to be used more typically in a B picture that is closer to its backward-motion reference picture than to its forward-motion reference picture). |

## -remarks

Certain members of this structure are constrained to specific values by the configuration established using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a> structure. After the picture-level parameters are conveyed using DXVA_PictureParameters, the picture decoding process is primarily governed by <a href="https://docs.microsoft.com/windows-hardware/drivers/display/macroblock-control-commands">macroblock control commands</a> formed using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_i_hostresiddiff_1">DXVA_MBctrl_I_HostResidDiff_1</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_i_offhostidct_1">DXVA_MBctrl_I_OffHostIDCT_1</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_p_hostresiddiff_1">DXVA_MBctrl_P_HostResidDiff_1</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_p_offhostidct_1">DXVA_MBctrl_P_OffHostIDCT_1</a> structures.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_i_hostresiddiff_1">DXVA_MBctrl_I_HostResidDiff_1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_i_offhostidct_1">DXVA_MBctrl_I_OffHostIDCT_1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_p_hostresiddiff_1">DXVA_MBctrl_P_HostResidDiff_1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_p_offhostidct_1">DXVA_MBctrl_P_OffHostIDCT_1</a>
 

 

