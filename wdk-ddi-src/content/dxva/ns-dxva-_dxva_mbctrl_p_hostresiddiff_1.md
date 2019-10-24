---
UID: NS:dxva._DXVA_MBctrl_P_HostResidDiff_1
title: _DXVA_MBctrl_P_HostResidDiff_1 (dxva.h)
description: The DXVA_MBctrl_P_HostResidDiff_1 structure is sent once per macroblock by the host decoder to the accelerator to specify macroblock control commands for most nonintra picture cases when using host-based IDCT.
old-location: display\dxva_mbctrl_p_hostresiddiff_1.htm
tech.root: display
ms.assetid: be67b423-32a1-4f30-9f2c-fa6347cc960f
ms.date: 05/10/2018
ms.keywords: "*LPDXVA_MBctrl_P_HostResidDiff_1, DXVA_MBctrl_P_HostResidDiff_1, DXVA_MBctrl_P_HostResidDiff_1 structure [Display Devices], _DXVA_MBctrl_P_HostResidDiff_1, display.dxva_mbctrl_p_hostresiddiff_1, dxva/DXVA_MBctrl_P_HostResidDiff_1, dxvaref_a97c973f-9673-4049-badd-648b1d0cc39c.xml"
ms.topic: struct
f1_keywords:
 - "dxva/DXVA_MBctrl_P_HostResidDiff_1"
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
- DXVA_MBctrl_P_HostResidDiff_1
product:
- Windows
targetos: Windows
req.typenames: DXVA_MBctrl_P_HostResidDiff_1
---

# _DXVA_MBctrl_P_HostResidDiff_1 structure


## -description


The DXVA_MBctrl_P_HostResidDiff_1 structure is sent once per macroblock by the host decoder to the accelerator to specify macroblock control commands for most nonintra picture cases when using <a href="https://docs.microsoft.com/windows-hardware/drivers/">host-based IDCT</a>.


## -struct-fields




### -field wMBaddress

Specifies the macroblock address of the current macroblock in raster scan order. For examples of macroblock addresses see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/macroblock-addresses">macroblock addresses</a>.


### -field wMBtype

Specifies the type of macroblock being processed. The following bits define the contents of <b>wMBtype</b>.

| **Bits** | **Description** | 
|:--|:--|
| 15 to 12 | MvertFieldSel_3 (bit 15, the most significant bit) through MvertFieldSel_0 (bit 12)<br/>Specifies vertical field selection for corresponding motion vectors sent later in the macroblock control command. For frame-based motion with a frame picture structure (for example, for H.261 and H.263), these bits must all be zero. The use of these bits is the same as that specified for the corresponding bits in Section 6.3.17.2 of MPEG-2. | 
| 11 | Reserved Bit. Must be zero. | 
| 10 | *HostResidDiff*<br/>Specifies whether spatial-domain residual difference decoded blocks are sent or whether transform coefficients are sent for off-host IDCT for the current macroblock.<br/>The HostResidDif flag is always equal to 1 in this structure. This flag must be zero if bConfigResidDiffHost is zero. This flag must be 1 if bConfigResidDiffAccelerator is zero. | 
| 9 and 8 | *MotionType*<br/>Specifies the motion type in the picture. For example, for frame-based motion with a frame picture structure (as in H.261), bit 9 must be 1 and bit 8 must be zero.<br/>The use of these bits corresponds directly to the use of frame_motion_type or field_motion_type bits in Section 6.3.17.1 and Tables 6-17 and 6-18 of MPEG-2 videowhen these bits are present in MPEG-2. The use of these bits are further explained in the following Remarks section. | 
| 7 and 6 | *MBscanMethod*<br/>This variable has no meaning and these bits should be set to zero in this structure. | 
| 5 | *FieldResidual*<br/>Indicates whether the residual difference blocks use a field IDCT structure as specified in MPEG-2.<br/>Must be 1 if the bPicStructure member of [DXVA_PictureParameters](https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_pictureparameters)  is 1 or 2. When used for MPEG-2, FieldResidual must be zero if the frame_pred_frame_DCT variable in the MPEG-2 syntax is 1, and must be equal to the dct_type variable in the MPEG-2 syntax if dct_type is present for the macroblock. | 
| 4 | *H261LoopFilter*<br/>Specifies whether the H.261 loop filter (Section 3.2.3 of H.261) is active for the current macroblock prediction. The H.261 loop filter is a separable 1/4, 1/2, 1/4 filter applied both horizontally and vertically to all six blocks in an H.261 macroblock, except at block edges where one of the taps would fall outside the block. In such cases, the filter is changed to have coefficients 0, 1, 0. Full arithmetic precision is retained with rounding to 8-bit integers at the output of the 2-D filter process (half-integer or higher values being rounded up). | 
| 3 | *Motion4MV*<br/>A variable indicating that forward motion uses a distinct motion vector for each of the four luminance blocks in the macroblock, as used in H.263 Annexes F and J. Motion4MV must be zero if MotionForward is zero or if the bPic4MVallowed member of [DXVA_PictureParameters](https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_pictureparameters)  is zero. |
| 2 | *MotionBackward*<br/>Used in the manner specified for the corresponding macroblock_motion_backward variable in MPEG-2. If the bPicBackwardPrediction member of DXVA_PictureParameters is zero, MotionBackward must be zero. The use of this bit is further explained in the following Remarks section. |
| 1 | *MotionForward*<br/>Used for the corresponding macroblock_motion_forward variable in MPEG-2. The use of this bit is further explained in the following Remarks section. | 
| 0 | *IntraMacroblock*<br/>Indicates that the macroblock is coded as intra, and no motion vectors are used for the current macroblock. Corresponds to macroblock_intrain MPEG-2. The use of this bit is further explained in the following Remarks section. | 


### -field dwMB_SNL

Specifies the number of skipped macroblocks to be generated following the current macroblock and indicates the location of the residual difference data for the blocks of the current macroblock. This member contains two variables: <i>MBskipsFollowing</i> in the most significant 8 bits, and <i>MBdataLocation</i> in the least significant 24 bits. <i>MBskipsFollowing</i> indicates the number of skipped macroblocks to be generated following the current macroblock. <i>MBdataLocation</i> is an index into the residual difference block data buffer. This index indicates the location of the residual difference data for the blocks of the current macroblock, expressed as a multiple of 32 bits.


### -field wPatternCode

Indicates whether <a href="https://docs.microsoft.com/windows-hardware/drivers/display/macroblock-oriented-picture-decoding">residual difference data</a> is sent for each block in the current macroblock. 

Bit (11-<i>i</i>) of <b>wPatternCode</b> (where bit zero is the least significant bits) indicates whether residual difference data is sent for block <i>i</i>, where <i>i</i> is the index of the block within the macroblock as specified in MPEG-2 figures 6-10, 6-11, and 6-12 (raster-scan order for Y, followed by 4:2:0 blocks of Cb in raster-scan order, followed by 4:2:0 blocks of Cr, followed by 4:2:2 blocks of Cb, followed by 4:2:2 blocks of Cr, followed by 4:4:4 blocks of Cb, followed by 4:4:4 blocks of Cr). The data for the coded blocks (those blocks having bit (11-<i>i</i>) equal to 1) is found in the residual coding buffer in the same indexing order (increasing <i>i</i>). For 4:2:0 MPEG-2 data, the value of <b>wPatternCode</b> corresponds to shifting the decoded value of the CBP (coded block pattern) to the left by six bit positions (those lower bit positions being used for 4:2:2 and 4:4:4 chroma formats).

If the <b>bConfigSpatialResidInterleaved </b>member of DXVA_ConfigPictureDecode is 1, host-based residual differences are sent in a chroma-interleaved form matching that of the YUV pixel format in use. In this case, each Cb and spatially corresponding Cr pair of blocks is treated as a single residual difference structure unit. This does not alter the value or meaning of <b>wPatternCode</b>, but it implies that both members of each pair of Cb and Cr data blocks are sent whenever either of these data blocks has the corresponding bit set in <b>wPatternCode</b>. If the bit in <b>wPatternCode</b> for a particular data block is zero, the corresponding residual difference data values must be sent as zero whenever this pairing necessitates sending a residual difference data block for a block with a <b>wPatternCode</b> bit equal to zero.


### -field wPC_Overflow

Specifies which blocks of the macroblock use overflow residual difference data.

When using host-based residual difference decoding with the <b>bPicOverflowBlocks</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_pictureparameters">DXVA_PictureParameters</a> equal to 1 and IntraMacroblock equal to zero (the 8-8 overflow method), <b>wPC_Overflow</b> contains the pattern code of the overflow blocks. (The pattern code is specified in the same manner as for <b>wPatternCode</b>.) The data for the coded overflow blocks (those blocks having bit (11-i) equal to 1) is found in the residual coding buffer in the same indexing order (increasing i).

 


### -field dwReservedBits2

Reserved bits used for packing and alignment. Must be zero.


### -field MVector

An array containing the value of the motion vector(s) for the macroblock, each motion vector is represented by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mvvalue">DXVA_MVvalue</a> structure.


## -remarks



Each skipped macroblock specified by <i>MBskipsFollowing </i>must be generated in a manner mathematically equivalent to incrementing the value of <b>wMBaddress</b> and then repeating the same macroblock control command.

The content of a macroblock control command with a nonzero value for <i>MBskipsFollowing</i> is equivalent (except for the value of <i>MBskipsFollowing</i>) to the content of the first of the series of skipped macroblocks. Thus, whenever <i>MBskipsFollowing</i> is not zero, the following structure members and variables must all be equal to zero: <i>Motion4MV, IntraMacroblock, </i><b>wPatternCode</b><i>, and </i><b>wPC_Overflow</b>. Each subsequent skipped macroblock is then generated in the same way as the first, except for incrementing the value of <b>wMBaddress</b>.

<i>MBdataLocation</i> must be zero for the first macroblock in the macroblock control command buffer. For macroblocks other than the first macroblock in the macroblock control command buffer, <i>MBdataLocation</i> may contain any value if <b>wPatternCode</b> is zero. When <b>wPatternCode</b> is zero, decoders are recommended but not required to set this value either to zero or to the same value as in the next macroblock control command.

For more information about how skipped macroblocks are generated, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/generating-skipped-macroblocks">Generating Skipped Macroblocks</a>.

Valid combinations of <i>IntraMacroblock</i>, <i>MotionForward</i>, <i>MotionBackward</i>, <i>MotionType</i>, <i>MvertFieldSel</i>, and <b>MVector</b> are shown in the tables in <a href="https://docs.microsoft.com/windows-hardware/drivers/display/first-part-of-macroblock-control-command-structure">First Part of Macroblock Control Command Structure</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_p_offhostidct_1">DXVA_MBctrl_P_OffHostIDCT_1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mvvalue">DXVA_MVvalue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_pictureparameters">DXVA_PictureParameters</a>
 

 

