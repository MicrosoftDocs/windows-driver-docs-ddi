---
UID: NS:dxva._DXVA_QmatrixData
title: _DXVA_QmatrixData (dxva.h)
description: The DXVA_QmatrixData structure is sent by the host decoder to the accelerator to load inverse-quantization matrix data for off-host bitstream compressed video picture decoding.
old-location: display\dxva_qmatrixdata.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXVA_QmatrixData structure"]
ms.keywords: "*LPDXVA_QmatrixData, DXVA_QmatrixData, DXVA_QmatrixData structure [Display Devices], LPDXVA_QmatrixData, LPDXVA_QmatrixData structure pointer [Display Devices], _DXVA_QmatrixData, display.dxva_qmatrixdata, dxva/DXVA_QmatrixData, dxva/LPDXVA_QmatrixData, dxvaref_96294cc5-1f6c-4632-bb98-df5e56bac34f.xml"
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
targetos: Windows
req.typenames: DXVA_QmatrixData, *LPDXVA_QmatrixData
f1_keywords:
 - _DXVA_QmatrixData
 - dxva/_DXVA_QmatrixData
 - LPDXVA_QmatrixData
 - dxva/LPDXVA_QmatrixData
 - DXVA_QmatrixData
 - dxva/DXVA_QmatrixData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dxva.h
api_name:
 - _DXVA_QmatrixData
 - LPDXVA_QmatrixData
 - DXVA_QmatrixData
---

# _DXVA_QmatrixData structure


## -description

The DXVA_QmatrixData structure is sent by the host decoder to the accelerator to load inverse-quantization matrix data for off-host bitstream compressed video picture decoding.

## -struct-fields

### -field bNewQmatrix

Indicates which new inverse-quantization matrices are present in an inverse-quantization matrix buffer. Each element in this array corresponds to an inverse-quantization matrix type and indicates whether a new inverse-quantization matrix of that type is present in the buffer. If any element in the <b>bNewQmatrix</b> array contains a value of 1, a new inverse-quantization matrix of the type specified for that array element follows in the inverse-quantization matrix buffer. The inverse-quantization matrices that can be used are as follows.

|NewQmatrix Element|Inverse-Quantization Matrix Type|
|--- |--- |
|0|Specifies intra-luminance quantization.|
|1|Specifies inter-luminance quantization.|
|2|Specifies intra-chrominance quantization.|
|3|Specifies inter-chrominance quantization.|

The value in <b>bNewQmatrix</b>[0] and <b>bNewQmatrix</b>[1] must not both be zero.

If the value for <b>bNewQmatrix</b>[2] or <b>bNewQmatrix</b>[3] is zero, then the following applies:

If <b>bNewQmatrix</b>[<i>i </i>- 2] is zero, the previous inverse-quantization matrix defined by the <i>i</i>th element must continue to be used by the accelerator.

If <b>bNewQmatrix</b>[<i>i </i>- 2] is 1, the inverse-quantization matrix defined by the <i>i</i>th element is set equal to the new inverse-quantization matrix for <i>i </i>- 2.

### -field Qmatrix

A two-dimensional array that specifies an inverse-quantization matrix buffer. This array is present only for each element in <b>bNewQmatrix</b> equal to 1. The matrix consists of (<b>bBlockWidthMinus1</b>+1) X (<b>bBlockHeightMinus1</b>+1) unsigned words (in which only the lower 8 bits of each word are used for the dominant video coding standards), where <b>bBlockWidthMinus1</b> and <b>bBlockHeightMinus1</b> are members of the <a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_pictureparameters">DXVA_PictureParameters</a> structure.

<div class="alert"><b>Note</b>  For MPEG-2 bitstreams, the data values within Qmatrix are in zigzag inverse scan order, as specified in subclause 7.3.1 and figure 7-2 of MPEG-2.</div>
<div> </div>

## -remarks

If the video coding does not need inverse-quantization matrices (for example, H.261 and H.263), inverse-quantization matrix buffers must not be sent. If the video coding does need inverse-quantization matrices, some value must be provided for these inverse-quantization matrices by the host prior to, or in conjunction with, the transfer of any bitstream data buffers at the start of the video decoding process.

No default values of inverse-quantization matrices may be assumed by the accelerator in the absence of any prior value sent by the host. The quantization matrix values must be sent explicitly, even if they contain values that are available by default in the relevant video coding specification.

Inverse-quantization matrix buffers are sent only when the <b>bConfigBitstreamRaw</b> member of the <a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a> structure is 1.

The order of the data values within the inverse-quantization matrix is as specified in the relevant video coding specification.

## -see-also

<a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_configpicturedecode">DXVA_ConfigPictureDecode</a>



<a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_pictureparameters">DXVA_PictureParameters</a>

