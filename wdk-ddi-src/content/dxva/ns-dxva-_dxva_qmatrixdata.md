---
UID: NS:dxva._DXVA_QmatrixData
title: "_DXVA_QmatrixData"
author: windows-driver-content
description: The DXVA_QmatrixData structure is sent by the host decoder to the accelerator to load inverse-quantization matrix data for off-host bitstream compressed video picture decoding.
old-location: display\dxva_qmatrixdata.htm
old-project: display
ms.assetid: 2cb96d6b-37f1-47dd-8135-66d3ead2dd64
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*LPDXVA_QmatrixData, DXVA_QmatrixData, DXVA_QmatrixData structure [Display Devices], LPDXVA_QmatrixData, LPDXVA_QmatrixData structure pointer [Display Devices], _DXVA_QmatrixData, display.dxva_qmatrixdata, dxva/DXVA_QmatrixData, dxva/LPDXVA_QmatrixData, dxvaref_96294cc5-1f6c-4632-bb98-df5e56bac34f.xml"
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
-	DXVA_QmatrixData
product: Windows
targetos: Windows
req.typenames: DXVA_QmatrixData, *LPDXVA_QmatrixData
---

# _DXVA_QmatrixData structure


## -description


The DXVA_QmatrixData structure is sent by the host decoder to the accelerator to load inverse-quantization matrix data for off-host bitstream compressed video picture decoding.


## -syntax


````
typedef struct _DXVA_QmatrixData {
  BYTE bNewQmatrix[4];
  WORD Qmatrix[4][DXVA_USUAL_BLOCK_WIDTH * DXVA_USUAL_BLOCK_HEIGHT];
} DXVA_QmatrixData, *LPDXVA_QmatrixData;
````


## -struct-fields




### -field bNewQmatrix

Indicates which new inverse-quantization matrices are present in an inverse-quantization matrix buffer. Each element in this array corresponds to an inverse-quantization matrix type and indicates whether a new inverse-quantization matrix of that type is present in the buffer. If any element in the <b>bNewQmatrix</b> array contains a value of 1, a new inverse-quantization matrix of the type specified for that array element follows in the inverse-quantization matrix buffer. The inverse-quantization matrices that can be used are as follows.

<table>
<tr>
<th>bNewQmatrix Element</th>
<th>Inverse-Quantization Matrix Type</th>
</tr>
<tr>
<td>
0

</td>
<td>
Specifies intra-luminance quantization.

</td>
</tr>
<tr>
<td>
1

</td>
<td>
Specifies inter-luminance quantization.

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Specifies intra-chrominance quantization.

</td>
</tr>
<tr>
<td>
3

</td>
<td>
Specifies inter-chrominance quantization.

</td>
</tr>
</table>
 

The value in <b>bNewQmatrix</b>[0] and <b>bNewQmatrix</b>[1] must not both be zero.

If the value for <b>bNewQmatrix</b>[2] or <b>bNewQmatrix</b>[3] is zero, then the following applies:

If <b>bNewQmatrix</b>[<i>i </i>- 2] is zero, the previous inverse-quantization matrix defined by the <i>i</i>th element must continue to be used by the accelerator.

If <b>bNewQmatrix</b>[<i>i </i>- 2] is 1, the inverse-quantization matrix defined by the <i>i</i>th element is set equal to the new inverse-quantization matrix for <i>i </i>- 2.


### -field Qmatrix

A two-dimensional array that specifies an inverse-quantization matrix buffer. This array is present only for each element in <b>bNewQmatrix</b> equal to 1. The matrix consists of (<b>bBlockWidthMinus1</b>+1) X (<b>bBlockHeightMinus1</b>+1) unsigned words (in which only the lower 8 bits of each word are used for the dominant video coding standards), where <b>bBlockWidthMinus1</b> and <b>bBlockHeightMinus1</b> are members of the <a href="..\dxva\ns-dxva-_dxva_pictureparameters.md">DXVA_PictureParameters</a> structure.

<div class="alert"><b>Note</b>  For MPEG-2 bitstreams, the data values within Qmatrix are in zigzag inverse scan order, as specified in subclause 7.3.1 and figure 7-2 of MPEG-2.</div>
<div> </div>

## -remarks



If the video coding does not need inverse-quantization matrices (for example, H.261 and H.263), inverse-quantization matrix buffers must not be sent. If the video coding does need inverse-quantization matrices, some value must be provided for these inverse-quantization matrices by the host prior to, or in conjunction with, the transfer of any bitstream data buffers at the start of the video decoding process.

No default values of inverse-quantization matrices may be assumed by the accelerator in the absence of any prior value sent by the host. The quantization matrix values must be sent explicitly, even if they contain values that are available by default in the relevant video coding specification.

Inverse-quantization matrix buffers are sent only when the <b>bConfigBitstreamRaw</b> member of the <a href="..\dxva\ns-dxva-_dxva_configpicturedecode.md">DXVA_ConfigPictureDecode</a> structure is 1.

The order of the data values within the inverse-quantization matrix is as specified in the relevant video coding specification.




## -see-also

<a href="..\dxva\ns-dxva-_dxva_configpicturedecode.md">DXVA_ConfigPictureDecode</a>



<a href="..\dxva\ns-dxva-_dxva_pictureparameters.md">DXVA_PictureParameters</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_QmatrixData structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

