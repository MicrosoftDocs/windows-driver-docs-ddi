---
UID: NS:dxva._DXVA_MBctrl_I_HostResidDiff_1
title: _DXVA_MBctrl_I_HostResidDiff_1 (dxva.h)
description: The DXVA_MBctrl_I_HostResidDiff_1 structure is sent once per macroblock by the host decoder to the accelerator to specify macroblock control commands for an intra picture.
old-location: display\dxva_mbctrl_i_hostresiddiff_1.htm
tech.root: display
ms.assetid: e2318d02-f52e-4b5b-86da-04df7b31b7d3
ms.date: 05/10/2018
ms.keywords: "*LPDXVA_MBctrl_I_HostResidDiff_1, DXVA_MBctrl_I_HostResidDiff_1, DXVA_MBctrl_I_HostResidDiff_1 structure [Display Devices], _DXVA_MBctrl_I_HostResidDiff_1, display.dxva_mbctrl_i_hostresiddiff_1, dxva/DXVA_MBctrl_I_HostResidDiff_1, dxvaref_9d7c8453-31ce-4788-908e-ac81c97d97f5.xml"
ms.topic: struct
f1_keywords:
 - "dxva/DXVA_MBctrl_I_HostResidDiff_1"
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
- DXVA_MBctrl_I_HostResidDiff_1
product:
- Windows
targetos: Windows
req.typenames: DXVA_MBctrl_I_HostResidDiff_1
---

# _DXVA_MBctrl_I_HostResidDiff_1 structure


## -description


The DXVA_MBctrl_I_HostResidDiff_1 structure is sent once per macroblock by the host decoder to the accelerator to specify macroblock control commands for an <a href="https://docs.microsoft.com/windows-hardware/drivers/">intra picture</a>.


## -struct-fields




### -field wMBaddress

Specifies the macroblock address of the current macroblock in raster scan order. For examples of macroblock addresses, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/macroblock-addresses">macroblock addresses</a>.


### -field wMBtype

Specifies the type of macroblock being processed. The following bits define macroblock processing.

| **Bits** | **Description** | 
|:--|:--|
| 15 to 12 | MvertFieldSel_3 (bit 15, the most significant bit) through MvertFieldSel_0 (bit 12)<br/>Specifies vertical field selection for corresponding motion vectors sent later in the macroblock control command. For frame-based motion with a frame picture structure (for example, for H.261 and H.263), these bits must all be zero. The bits in MvertFieldSel_0, *MvertFieldSel_1,* MvertFieldSel_2, and MvertFieldSel_3 correspond to the motion_vertical_field_select[r][s] bits in Section 6.3.17.2 of MPEG-2. | 
| 11 | *Reserved Bit*<br/>Must be zero. | 
| 10 | *HostResidDiff*<br/>Specifies whether spatial-domain residual difference decoded blocks are sent or whether transform coefficients are sent for off-host IDCT for the current macroblock.<br/>HostResidDiff is always equal to 1 in this structure. This flag must be zero if bConfigResidDiffHost is zero. This flag must be 1 if bConfigResidDiffAccelerator is zero. The bConfigResidDiffHost and bConfigResidDiffAccelerator members are contained in the [DXVA_ConfigPictureDecode](https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode)  structure. | 
| 9 and 8 | *MotionType*<br/>Must be zero. | 
| 7 and 6 | *MBscanMethod*<br/>These bits have no meaning and should be set to zero. | 
| 5 | *FieldResidual*<br/>Indicates whether the residual difference blocks use a field IDCT structure as specified in MPEG-2.<br/>Must be 1 if the bPicStructure member of DXVA_PictureParameters is 1 or 2. When used for MPEG-2, FieldResidual must be zero if the frame_pred_frame_DCT flag in the MPEG-2 syntax is 1, and must be equal to the dct_type variable of the MPEG-2 syntax if dct_type is present for the macroblock. | 
| 4 | *H261LoopFilter*<br/>Must be zero. | 
| 3 | *Motion4MV*<br/>Must be zero. | 
| 2 | *MotionBackward*<br/>Must be zero. | 
| 1 | *MotionForward*<br/>Must be zero. | 
| 0 | *IntraMacroblock*<br/>Must be 1. | 





### -field dwMB_SNL

Specifies the number of skipped macroblocks to be generated following the current macroblock, and indicates the location of the residual difference data for the blocks of the current macroblock. This member contains two variables: <i>MBskipsFollowing</i> in the most significant 8 bits, and <i>MBdataLocation</i> in the least significant 24 bits. <i>MBskipsFollowing</i> indicates the number of skipped macroblocks to be generated following the current macroblock. <i>MBdataLocation</i> is an index into the residual difference block data buffer. This index indicates the location of the residual difference data for the blocks of the current macroblock, expressed as a multiple of 32 bits.


### -field wPatternCode

Indicates whether residual difference data is sent for each block in the macroblock. In an intra picture, residual difference data is sent for every block in the macroblock. The bits in <b>wPatternCode</b> that refer to all blocks of the current macroblock must be 1 in this structure. 

Bit (11-<i>i</i>) of <b>wPatternCode</b> (where bit zero is the least significant bit) indicates whether residual difference data is sent for block <i>i</i>, where <i>i</i> is the index of the block within the macroblock as specified in MPEG-2 figures 6-10, 6-11, and 6-12 (raster-scan order for Y, followed by 4:2:0 blocks of Cb in raster-scan order, followed by 4:2:0 blocks of Cr, followed by 4:2:2 blocks of Cb, followed by 4:2:2 blocks of Cr, followed by 4:4:4 blocks of Cb, followed by 4:4:4 blocks of Cr). The data for the coded blocks (those blocks having bit (11<i>i</i>) equal to 1) is found in the residual coding buffer in the same indexing order (increasing <i>i</i>). For 4:2:0 MPEG-2 data, the value of <b>wPatternCode</b> corresponds to shifting the decoded value of the CBP (coded block pattern) to the left by six bit positions (those lower bit positions being used for 4:2:2 and 4:4:4 chroma formats).

If the <b>bConfigSpatialResidInterleaved</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a> structure is 1, host-based residual differences are sent in a chroma-interleaved form matching that of the YUV pixel format in use. In this case, each Cb and spatially corresponding Cr pair of blocks is treated as a single residual difference structure unit. This does not alter the value or meaning of <b>wPatternCode</b>, but it implies that both members of each pair of Cb and Cr data blocks are sent whenever either of these data blocks has the corresponding bit set in <b>wPatternCode</b>. If the bit in <b>wPatternCode</b> for a particular data block is zero, the corresponding residual difference data values must be sent as zero whenever this pairing necessitates sending a residual difference data block for a block with a <b>wPatternCode</b> bit equal to zero.


### -field wPC_Overflow

Must be zero.


### -field dwReservedBits2

Reserved bits used for packing and alignment. Must be zero.


## -remarks



Skipped macroblocks are not used by intra pictures, so the <i>MBskipsFollowing</i> variable must be zero. The <i>MBdataLocation</i> variable must be zero for the first macroblock in the macroblock control command buffer. For more information about how skipped macroblocks are generated, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/generating-skipped-macroblocks">Generating Skipped Macroblocks</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_mbctrl_i_offhostidct_1">DXVA_MBctrl_I_OffHostIDCT_1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_pictureparameters">DXVA_PictureParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_tcoefsingle">DXVA_TCoefSingle</a>
 

 

