---
UID: NS:dxva._DXVA_MBctrl_I_OffHostIDCT_1
title: "_DXVA_MBctrl_I_OffHostIDCT_1"
author: windows-driver-content
description: The DXVA_MBctrl_I_OffHostIDCT_1 structure is sent once per macroblock by the host decoder to the accelerator to specify macroblock control commands for 4:2:0 intra pictures when using off-host IDCT.
old-location: display\dxva_mbctrl_i_offhostidct_1.htm
old-project: display
ms.assetid: c088a923-0600-48ae-8d3e-95b6bbcb59c7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPDXVA_MBctrl_I_OffHostIDCT_1, DXVA_MBctrl_I_OffHostIDCT_1, DXVA_MBctrl_I_OffHostIDCT_1 structure [Display Devices], _DXVA_MBctrl_I_OffHostIDCT_1, display.dxva_mbctrl_i_offhostidct_1, dxva/DXVA_MBctrl_I_OffHostIDCT_1, dxvaref_2ad46e82-c043-45f2-8ec9-e174e9b21e6e.xml"
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
-	DXVA_MBctrl_I_OffHostIDCT_1
product: Windows
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
<i>MvertFieldSel_3</i> (bit 15, the most significant bit) through <i>MvertFieldSel_0</i> (bit 12)

Must be zero. 

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

The <i>HostResidDiff </i>flag is always equal to zero in this structure. This flag must be zero if <b>bConfigResidDiffHost</b> is zero. This flag must be 1 if <b>bConfigResidDiffAccelerator</b> is zero. The <b>bConfigResidDiffHost</b> and <b>bConfigResidDiffAccelerator</b> members are contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563133">DXVA_ConfigPictureDecode</a> structure.

</td>
</tr>
<tr>
<td>
9 and 8

</td>
<td>
<i>MotionType</i>

This does not apply to intra pictures. Both bits must be zero.

</td>
</tr>
<tr>
<td>
7 and 6

</td>
<td>
<i>MBscanMethod</i>

Specifies the scan method of the macroblock control command. This must be equal to <b>bPicScanMethod</b> if <b>bPicScanFixed</b> is 1. 

If <b>bConfigHostInverseScan</b> is zero, <i>MBscanMethod</i> is one of the following values:

<ul>
<li>
 Zero âˆ’ zigzag scan (MPEG-2 Figure 7-2)

</li>
<li>
 1 âˆ’ alternate-vertical scan (MPEG-2 Figure 7-3)

</li>
<li>
 2 âˆ’ alternate-horizontal scan (H.263 Figure I.2 Part a)

</li>
</ul>
If <b>bConfigHostInverseScan</b> is 1, <i>MBscanMethod</i> is equal to 3, which is an arbitrary scan with absolute coefficient address.

<b>bPicScanMethod</b> and <b>bPicScanFixed</b> are members of <a href="https://msdn.microsoft.com/library/windows/hardware/ff564012">DXVA_PictureParameters</a>. <b>bConfigHostInverseScan</b> is a member of DXVA_ConfigPictureDecode.

</td>
</tr>
<tr>
<td>
5

</td>
<td>
<i>FieldResidual</i>

Indicates whether the residual difference blocks use a field IDCT structure as specified in MPEG-2.

Must be 1 if the <b>bPicStructure</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff564012">DXVA_PictureParameters</a> is 1 or 2. When used for MPEG-2, <i>FieldResidual</i> must be zero if the <i>frame_pred_frame_DCT</i> flag in the MPEG-2 syntax is 1, and must be equal to the <i>dct_type</i> element of the MPEG-2 syntax if <i>dct_type</i> is present for the macroblock.

</td>
</tr>
<tr>
<td>
4

</td>
<td>
<i>H261LoopFilter</i>

Must be zero. 

</td>
</tr>
<tr>
<td>
3

</td>
<td>
<i>Motion4MV</i>

Must be zero. 

</td>
</tr>
<tr>
<td>
2

</td>
<td>
<i>MotionBackward</i>

Must be zero. 

</td>
</tr>
<tr>
<td>
1

</td>
<td>
<i>MotionForward</i>

Must be zero. 

</td>
</tr>
<tr>
<td>
0

</td>
<td>
<i>IntraMacroblock</i>

Must be 1. 

</td>
</tr>
</table>
 


### -field dwMB_SNL





######### 


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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_MBctrl_I_OffHostIDCT_1 structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

