---
UID: NS:dxva._DXVA_PicParams_HEVC_RangeExt
tech.root: display
title: DXVA_PicParams_HEVC_RangeExt
ms.date: 10/25/2024
targetos: Windows
description: Learn more about the DXVA_PicParams_HEVC_RangeExt structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dxva.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, verion 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXVA_PicParams_HEVC_RangeExt, *LPDXVA_PicParams_HEVC_RangeExt
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dxva.h
api_name:
 - _DXVA_PicParams_HEVC_RangeExt
 - LPDXVA_PicParams_HEVC_RangeExt
 - DXVA_PicParams_HEVC_RangeExt
f1_keywords:
 - _DXVA_PicParams_HEVC_RangeExt
 - dxva/_DXVA_PicParams_HEVC_RangeExt
 - LPDXVA_PicParams_HEVC_RangeExt
 - dxva/LPDXVA_PicParams_HEVC_RangeExt
 - DXVA_PicParams_HEVC_RangeExt
 - dxva/DXVA_PicParams_HEVC_RangeExt
dev_langs:
 - c++
helpviewer_keywords:
 - _DXVA_PicParams_HEVC_RangeExt
---

## -description

The **DXVA_PicParams_HEVC_RangeExt** structure provides the picture-level parameters of a compressed picture for HEVC video decoding.

## -struct-fields

### -field params

### -field transform_skip_rotation_enabled_flag

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly.

### -field transform_skip_context_enabled_flag

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly.

### -field implicit_rdpcm_enabled_flag

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly.

### -field explicit_rdpcm_enabled_flag

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly.

### -field extended_precision_processing_flag

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly.

### -field intra_smoothing_disabled_flag

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly.

### -field persistent_rice_adaptation_enabled_flag

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly.

### -field high_precision_offsets_enabled_flag

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly.

### -field cabac_bypass_alignment_enabled_flag

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly.

### -field cross_component_prediction_enabled_flag

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly.

### -field chroma_qp_offset_list_enabled_flag

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly.

### -field ReservedBits8

Reserved bit field.

### -field dwRangeExtensionFlags

Range extension flags.

### -field diff_cu_chroma_qp_offset_depth

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly. When the **chroma_qp_offset_list_enabled_flag** is 0, this value will be 0.

### -field log2_sao_offset_scale_luma

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly.

### -field log2_sao_offset_scale_chroma

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly.

### -field log2_max_transform_skip_block_size_minus2

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly.

### -field cb_qp_offset_list[6]

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly. When the **chroma_qp_offset_list_enabled_flag** is 0, this value will be 0.

### -field cr_qp_offset_list[6]

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly. When the **chroma_qp_offset_list_enabled_flag** is 0, this value will be 0.

### -field chroma_qp_offset_list_len_minus1

Corresponds to the syntax element of the same name in the HEVC specification and affects the decoding process accordingly.

### -field ReservedBits9

Reserved.

## -remarks

This structure is used when bDXVA_Func is 1 and the buffer type is DXVA2_PictureParametersBufferType (in DXVA 2.0). Note that **DXVA_PicParams_HEVC_RangeExt** is strictly an addition to [**DXVA_PicParams_HEVC**](/windows/win32/medfound/dxva-picparams-hevc); the first part of each structure is identical.  For the existing profiles **DXVA_ModeHEVC_VLD_Main** and **DXVA_ModeHEVC_VLD_Main10** accelerators are free to ignore the extra bytes in **DXVA_PicParams_HEVC_RangeExt**.

## -see-also

[**DXVA_PicParams_HEVC**](/windows/win32/medfound/dxva-picparams-hevc)
