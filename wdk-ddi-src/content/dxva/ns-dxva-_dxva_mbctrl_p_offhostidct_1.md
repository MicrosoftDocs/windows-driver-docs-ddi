---
UID: NS:dxva._DXVA_MBctrl_P_OffHostIDCT_1
title: "_DXVA_MBctrl_P_OffHostIDCT_1"
author: windows-driver-content
description: The DXVA_MBctrl_P_OffHostIDCT_1 structure is sent once per macroblock by the host decoder to the accelerator to specify macroblock control commands for most nonintra pictures using off-host IDCT.
old-location: display\dxva_mbctrl_p_offhostidct_1.htm
old-project: display
ms.assetid: 53a474a8-6cbd-4fe0-84d2-bf557b86ed71
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*LPDXVA_MBctrl_P_OffHostIDCT_1, DXVA_MBctrl_P_OffHostIDCT_1, DXVA_MBctrl_P_OffHostIDCT_1 structure [Display Devices], _DXVA_MBctrl_P_OffHostIDCT_1, display.dxva_mbctrl_p_offhostidct_1, dxva/DXVA_MBctrl_P_OffHostIDCT_1, dxvaref_5dae57d5-3e27-4928-8fd2-4c9cdad0285b.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dxva.h
api_name:
-	DXVA_MBctrl_P_OffHostIDCT_1
product: Windows
targetos: Windows
req.typenames: DXVA_MBctrl_P_OffHostIDCT_1
---

# _DXVA_MBctrl_P_OffHostIDCT_1 structure


## -description


The DXVA_MBctrl_P_OffHostIDCT_1 structure is sent once per macroblock by the host decoder to the accelerator to specify macroblock control commands for most nonintra pictures using off-host IDCT.


## -struct-fields




### -field wMBaddress

Specifies the macroblock address of the current macroblock in raster scan order. For examples of macroblock addresses see <a href="https://msdn.microsoft.com/f04c5462-db7c-4917-b8ef-22a630c82994">macroblock addresses</a>.


### -field wMBtype

Specifies the type of macroblock being processed. The following bits define macroblock processing.

<table>
<tr>
<th>Bits</th>
<th>Description</th>
</tr>
<tr>
<td>
15 to 12

</td>
<td>
<i>MvertFieldSel_</i>3 (bit 15 the most significant bit) through <i>MvertFieldSel</i>_0 (bit 12)

Specifies vertical field selection for corresponding motion vectors sent later in the macroblock control command. For frame-based motion with a frame picture structure (for example, for H.261 and H.263), these bits must all be zero. The use of these bits is the same as that specified for the corresponding bits in Section 6.3.17.2 of MPEG-2.

</td>
</tr>
<tr>
<td>
11

</td>
<td>
<i>Reserved Bit</i>

Must be zero.

</td>
</tr>
<tr>
<td>
10

</td>
<td>
<i>HostResidDiff</i>

Specifies whether spatial-domain residual difference decoded blocks are sent or whether transform coefficients are sent for off-host IDCT for the current macroblock.

This flag must be zero if <b>bConfigResidDiffHost</b> is zero. This flag must be 1 if <b>bConfigResidDiffAccelerator</b> is zero. This flag is always equal to zero in DXVA_MBctrl_P_OffHostIDCT_1.

</td>
</tr>
<tr>
<td>
9 and 8

</td>
<td>
<i>MotionType</i>

Specifies the motion type in the picture. For example, for frame-based motion with a frame picture structure (as in H.261), bit 9 must be 1 and bit 8 must be zero.

The use of these bits corresponds directly to the use of <i>frame_motion_type</i> or <i>field_motion_type bits</i> in MPEG-2 when these bits are present in MPEG-2. The use of these bits are further explained in the following <b>Remarks</b> section.

</td>
</tr>
<tr>
<td>
7 and 6

</td>
<td>
<i>MBscanMethod</i>

Specifies the scan method to be used.

This must be equal to <b>bPicScanMethod</b> if <b>bPicScanFixed</b> is 1. 

If <b>bConfigHostInverseScan</b> is zero, <i>MBscanMethod</i> must be one of the following values:

<ul>
<li>
Bit 6 is zero and bit 7 is zero for zigzag scan (MPEG-2 Figure 7-2).

</li>
<li>
Bit 6 is 1 and bit 7 is zero for alternate-vertical scan.

</li>
<li>
Bit 6 is zero and bit 7 is 1 for alternate-horizontal scan.

</li>
<li>
If <b>bConfigHostInverseScan</b> is 1, <i>MBscanMethod</i> must be equal to the following value:

</li>
<li>
Bit 6 is 1 and bit 7 is 1 for arbitrary scan with absolute coefficient address. 

</li>
</ul>
Both <b>bPicScanMethod</b> and <b>bPicScanFixed</b> are members of <a href="https://msdn.microsoft.com/library/windows/hardware/ff564012">DXVA_PictureParameters</a>. <b>bConfigHostInverseScan</b> is a member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563133">DXVA_ConfigPictureDecode</a>.

</td>
</tr>
<tr>
<td>
5

</td>
<td>
<i>FieldResidual</i>

Indicates whether the residual difference blocks use a field IDCT structure as specified in MPEG-2.

This flag must be 1 if the <b>bPicStructure</b> member of DXVA_PictureParameters is 1 or 2. 

When used for MPEG-2, <i>FieldResidual</i> must be zero if the <i>frame_pred_frame_DCT</i> flag in the MPEG-2 syntax is 1, and must be equal to the <i>dct_type element</i> of the MPEG-2 syntax if <i>dct_type</i> is present for the macroblock.

</td>
</tr>
<tr>
<td>
4

</td>
<td>
<i>H261LoopFilter</i>

Specifies whether the H.261 loop filter (Section 3.2.3 of H.261) is active for the current macroblock prediction. The H.261 loop filter is a separable Â¼, Â½, Â¼ filter applied both horizontally and vertically to all six blocks in an H.261 macroblock, except at block edges where one of the taps would fall outside the block. In such cases, the filter is changed to have coefficients 0, 1, 0. Full arithmetic precision is retained with rounding to 8-bit integers at the output of the 2-D filter process (half-integer or higher values being rounded up).

</td>
</tr>
<tr>
<td>
3

</td>
<td>
<i>Motion4MV</i>

Indicates that forward motion uses a distinct motion vector for each of the four luminance blocks in the macroblock, as used in H.263 Annexes F and J.<i>Motion4MV</i> must be zero if <i>MotionForward</i> is zero or if the <b>bPic4MVallowed</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff564012">DXVA_PictureParameters</a> is zero.

</td>
</tr>
<tr>
<td>
2

</td>
<td>
<i>MotionBackward</i>

Used as specified for the corresponding <i>macroblock_motion_backward</i> parameter in MPEG-2. If the <b>bPicBackwardPrediction</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff564012">DXVA_PictureParameters</a> is zero, <i>MotionBackward</i> must be zero. The use of this bit is further explained in the following <b>Remarks</b> section.

</td>
</tr>
<tr>
<td>
1

</td>
<td>
<i>MotionForward</i>

Used as specified for the corresponding <i>macroblock_motion_forward</i> in MPEG-2. The use of this bit is further explained in the following <b>Remarks</b> section.

</td>
</tr>
<tr>
<td>
0

</td>
<td>
<i>IntraMacroblock</i>

Indicates that the macroblock is coded as intra, and no motion vectors are used for the current macroblock. Corresponds to <i>macroblock_intra</i> in MPEG-2. The use of this bit is further explained in the following <b>Remarks</b> section.

</td>
</tr>
</table>
 


### -field dwMB_SNL

Specifies the number of skipped macroblocks to be generated following the current macroblock and indicates the location of the residual difference data for the blocks of the current macroblock. This member contains two variables: <i>MBskipsFollowing</i> in the most significant 8 bits and <i>MBdataLocation</i> in the least significant 24 bits. <i>MBskipsFollowing</i> indicates the number of skipped macroblocks to be generated following the current macroblock. <i>MBdataLocation</i> is an index into the IDCT residual difference block data buffer. This index indicates the location of the residual difference data for the blocks of the current macroblock, expressed as a multiple of 32 bits.


### -field wPatternCode

Indicates whether residual difference data is sent for each block in the macroblock.

Bit (11-<i>i</i>) of <b>wPatternCode</b> (where <i>i</i> is the index of the block within the macroblock and bit 0 represents the least significant bit) indicates whether residual difference data is sent for block <i>i</i> (See <a href="https://msdn.microsoft.com/7a416992-04d3-4307-83b3-9fb94c17d60e">Macroblock-Oriented Picture Decoding</a> for more information)<i>.</i> The value <i>i</i> is the index of the block within the macroblock as specified in MPEG-2 figures 6-10, 6-11, and 6-12 (raster-scan order for Y, followed by 4:2:0 blocks of Cb in raster-scan order, followed by 4:2:0 blocks of Cr, followed by 4:2:2 blocks of Cb, followed by 4:2:2 blocks of Cr, followed by 4:4:4 blocks of Cb, followed by 4:4:4 blocks of Cr). The data for the coded blocks (blocks having bit (11-<i>i</i>) equal to 1) is found in the residual coding buffer in the same indexing order (increasing <i>i</i>). For 4:2:0 MPEG-2 data, the value of <b>wPatternCode</b> corresponds to shifting the decoded value of CBP to the left by six bit positions (those lower bit positions being used for 4:2:2 and 4:4:4 chroma formats).

If the <b>bConfigSpatialResidInterleaved </b>member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563133">DXVA_ConfigPictureDecode</a> is 1, host-based residual differences are sent in a chroma-interleaved form matching that of the YUV pixel format in use. In this case, each Cb and spatially corresponding Cr pair of blocks is treated as a single residual difference data structure unit. This does not alter the value or meaning of <b>wPatternCode</b>, but it implies that both members of each pair of Cb and Cr data blocks are sent whenever either of these data blocks has the corresponding bit set in <b>wPatternCode</b>. If the bit in <b>wPatternCode</b> for a particular data block is zero, the corresponding residual difference data values must be sent as zero whenever this pairing requires sending a residual difference data block for a block with a <b>wPatternCode</b> bit equal to zero.


### -field bNumCoef

Each value in the <b>bNumCoef</b> array indicates the number of coefficients in the residual difference data buffer for each block <i>i</i> of the macroblock. 

The array subscript <i>i</i> is the index of the block within the macroblock as specified in MPEG-2 video Figures 6-10, 6-11, and 6-12 (raster-scan order for Y, followed by Cb, followed by Cr). 

This member is used only when the <i>HostResidDiff</i> flag (bit 10 in <b>wMBtype</b>) is zero and <b>bChromaFormat</b> is 1 (4:2:0). If used in 4:2:2 or 4:4:4 formats, it would increase the size of typical macroblock control commands past a critical memory alignment boundary. As a result, the <i>TCoefEOB</i> bit within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564060">DXVA_TCoefSingle</a> structure is used for determining the number of coefficients in each block in non-4:2:0 cases.

The purpose of <b>bNumCoef</b> is to indicate the quantity of data present for each block in the residual difference data buffer, expressed as the number of coefficients present. When the <b>bConfig4GroupedCoefs</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563133">DXVA_ConfigPictureDecode</a> structure is 1, <b>bNumCoef</b> may contain either the actual number of coefficients sent for the block or that value rounded up to be a multiple of four. The data for these coefficients is found in the residual difference buffer in the same order.


### -field MVector

An array containing the value of the motion vector(s) for the macroblock, each represented using a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564004">DXVA_MVvalue</a> structure.


## -remarks



Each skipped macroblock specified by <i>MBskipsFollowing </i>must be generated in a manner mathematically equivalent to incrementing the value of <b>wMBaddress</b> and then repeating the same macroblock control command. Any macroblock control command with a nonzero value for <i>MBskipsFollowing</i> specifies how motion-compensated prediction is to be performed for each macroblock to be skipped, and is equivalent (except for the value of <i>MBskipsFollowing</i>) to an explicit nonskip specification of the generation of the first of the series of skipped macroblocks. Thus, whenever <i>MBskipsFollowing</i> is not zero, the following values must all be equal to zero: <i>Motion4MV</i>, <i>IntraMacroblock</i>, and <b>bNumCoef</b>.

<i>MBdataLocation </i>is an index into the IDCT residual difference block data buffer, indicating the location of the residual difference data for the blocks of the current macroblock, expressed as a multiple of 32 bits. Must be zero for the first macroblock in the macroblock control command buffer. <i>MBdataLocation</i> may contain any value if <b>wPatternCode</b> is zero. When <b>wPatternCode</b> is zero, decoders are recommended but not required to set this value either to zero or to the same value as in the next macroblock control command.

For more information about how skipped macroblocks are generated, see <a href="https://msdn.microsoft.com/98ea004b-347d-4299-a23c-da0a9d0e844f">Generating Skipped Macroblocks</a>.

Valid combinations of <i>IntraMacroblock</i>, <i>MotionForward</i>, <i>MotionBackward</i>, <i>MotionType</i>, <i>MvertFieldSel</i>, and <b>MVector</b> are shown in the tables in <a href="https://msdn.microsoft.com/b282adac-3bf3-4477-a817-371d37b174a5">First Part of Macroblock Control Command Structure</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563133">DXVA_ConfigPictureDecode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563993">DXVA_MBctrl_P_HostResidDiff_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564004">DXVA_MVvalue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564012">DXVA_PictureParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564060">DXVA_TCoefSingle</a>
 

 

