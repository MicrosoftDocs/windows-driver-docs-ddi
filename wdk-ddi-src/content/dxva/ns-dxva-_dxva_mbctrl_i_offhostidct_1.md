---
UID: NS:dxva._DXVA_MBctrl_I_OffHostIDCT_1
title: "_DXVA_MBctrl_I_OffHostIDCT_1"
author: windows-driver-content
description: The DXVA_MBctrl_I_OffHostIDCT_1 structure is sent once per macroblock by the host decoder to the accelerator to specify macroblock control commands for 4:2:0 intra pictures when using off-host IDCT.
old-location: display\dxva_mbctrl_i_offhostidct_1.htm
tech.root: display
ms.assetid: c088a923-0600-48ae-8d3e-95b6bbcb59c7
ms.date: 05/10/2018
ms.keywords: "*LPDXVA_MBctrl_I_OffHostIDCT_1, DXVA_MBctrl_I_OffHostIDCT_1, DXVA_MBctrl_I_OffHostIDCT_1 structure [Display Devices], _DXVA_MBctrl_I_OffHostIDCT_1, display.dxva_mbctrl_i_offhostidct_1, dxva/DXVA_MBctrl_I_OffHostIDCT_1, dxvaref_2ad46e82-c043-45f2-8ec9-e174e9b21e6e.xml"
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
-	DXVA_MBctrl_I_OffHostIDCT_1
product:
- Windows
targetos: Windows
req.typenames: DXVA_MBctrl_I_OffHostIDCT_1
---

# _DXVA_MBctrl_I_OffHostIDCT_1 structure


## -description


The DXVA_MBctrl_I_OffHostIDCT_1 structure is sent once per macroblock by the host decoder to the accelerator to specify macroblock control commands for 4:2:0 intra pictures when using off-host IDCT. 


## -struct-fields




### -field wMBaddress

Specifies the macroblock address of the current macroblock in raster scan order. For examples of macroblock addresses see <a href="https://msdn.microsoft.com/f04c5462-db7c-4917-b8ef-22a630c82994">macroblock addresses</a>.


### -field wMBtype

Specifies the type of macroblock being processed. The following bits define macroblock processing.

| **Bits** | **Description** | 
|:--|:--|
| 15 to 12 | MvertFieldSel_3 (bit 15, the most significant bit) through MvertFieldSel_0 (bit 12)<br/>Must be zero. | 
| 11 | *Reserved Bit*<br/>Must be zero. | 
| 10 | *HostResidDiff*<br/>Specifies whether spatial-domain residual difference decoded blocks are sent or whether transform coefficients are sent for off-host IDCT for the current macroblock.<br/>The HostResidDiff flag is always equal to zero in this structure. This flag must be zero if bConfigResidDiffHost is zero. This flag must be 1 if bConfigResidDiffAccelerator is zero. The bConfigResidDiffHost and bConfigResidDiffAccelerator members are contained in the [DXVA_ConfigPictureDecode](https://msdn.microsoft.com/library/windows/hardware/ff563133)  structure. | 
| 9 and 8 | *MotionType*<br/>This does not apply to intra pictures. Both bits must be zero. | 
| 7 and 6 | *MBscanMethod*<br/>Specifies the scan method of the macroblock control command. This must be equal to bPicScanMethod if bPicScanFixed is 1.<br/>If bConfigHostInverseScan is zero, MBscanMethod is one of the following values:<ul><li>Zero âˆ’ zigzag scan (MPEG-2 Figure 7-2)</li><li>1 âˆ’ alternate-vertical scan (MPEG-2 Figure 7-3)</li><li>2 âˆ’ alternate-horizontal scan (H.263 Figure I.2 Part a)</li></ul>If bConfigHostInverseScan is 1, MBscanMethod is equal to 3, which is an arbitrary scan with absolute coefficient address. bPicScanMethod and bPicScanFixed are members of [DXVA_PictureParameters](https://msdn.microsoft.com/library/windows/hardware/ff564012) . bConfigHostInverseScan is a member of DXVA_ConfigPictureDecode. |
| 5 | *FieldResidual*<br/>Indicates whether the residual difference blocks use a field IDCT structure as specified in MPEG-2.<br/>Must be 1 if the bPicStructure member of [DXVA_PictureParameters](https://msdn.microsoft.com/library/windows/hardware/ff564012)  is 1 or 2. When used for MPEG-2, FieldResidual must be zero if the frame_pred_frame_DCT flag in the MPEG-2 syntax is 1, and must be equal to the dct_type element of the MPEG-2 syntax if dct_type is present for the macroblock. | 
| 4 | *H261LoopFilter*<br/>Must be zero. | 
| 3 | *Motion4MV*<br/>Must be zero. | 
| 2 | *MotionBackward*<br/>Must be zero. | 
| 1 | *MotionForward*<br/>Must be zero. | 
| 0 | *IntraMacroblock*<br/>Must be 1. | 

### -field dwMB_SNL


### -field wPatternCode

Indicates whether residual difference data is sent for each block in the macroblock. In an intra picture, residual difference data is sent for every block in the macroblock. The bits in <b>wPatternCode</b> that refer to all blocks of the current macroblock must be 1 in DXVA_MBctrl_I_OffHostIDCT_1.

Bit (11-<i>i</i>) of <b>wPatternCode</b> (where bit 0 is the least significant bit) indicates whether residual difference data is sent for block <i>i</i>, where <i>i</i> is the index of the block within the macroblock as specified in MPEG-2 figures 6-10, 6-11, and 6-12 (raster scan order for Y, followed by 4:2:0 blocks of Cb in raster scan order, followed by 4:2:0 blocks of Cr, followed by 4:2:2 blocks of Cb, followed by 4:2:2 blocks of Cr, followed by 4:4:4 blocks of Cb, followed by 4:4:4 blocks of Cr). The data for the coded blocks (those blocks having bit (11-<i>i</i>) equal to 1) is found in the residual coding buffer in the same indexing order (increasing <i>i</i>). For 4:2:0 MPEG-2 data, the value of <b>wPatternCode</b> corresponds to shifting the decoded value of CBP (coded block pattern) to the left by six bit positions (those lower-bit positions being used for 4:2:2 and 4:4:4 chroma formats).


### -field bNumCoef

Each value in the <b>bNumCoef</b> array indicates the number of coefficients in the residual difference data buffer for each block <i>i</i> of the macroblock. 

The array subscript <i>i</i> is the index of the block within the macroblock as specified in MPEG-2 video Figures 6-10, 6-11, and 6-12 (raster-scan order for Y, followed by Cb, followed by Cr). 

This member is used only when the <i>HostResidDiff</i> flag (bit 10 in <b>wMBtype</b>) is zero, and <b>bChromaFormat</b> is 1 (4:2:0). If used in 4:2:2 or 4:4:4 formats, it would increase the size of typical macroblock control commands past a critical memory alignment boundary. As a result, the <i>TCoefEOB</i> bit within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564060">DXVA_TCoefSingle</a> structure is used for determining the number of coefficients in each block in non-4:2:0 cases.

The purpose of <b>bNumCoef</b> is to indicate the quantity of data present for each block in the residual difference data buffer, expressed as the number of coefficients present. When the <b>bConfig4GroupedCoefs</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563133">DXVA_ConfigPictureDecode</a> structure is 1, <b>bNumCoef</b> may contain either the actual number of coefficients sent for the block or that value rounded up to be a multiple of four. The data for these coefficients is found in the residual difference buffer in the same order.


## -remarks



Skipped macroblocks are not used by intra pictures, so the <i>MBskipsFollowing</i> variable must be zero. The <i>MBdataLocation</i> variable must be zero for the first macroblock in the macroblock control command buffer. For more information about how skipped macroblocks are generated, see <a href="https://msdn.microsoft.com/98ea004b-347d-4299-a23c-da0a9d0e844f">Generating Skipped Macroblocks</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563133">DXVA_ConfigPictureDecode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563983">DXVA_MBctrl_I_HostResidDiff_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564012">DXVA_PictureParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564060">DXVA_TCoefSingle</a>
 

 

