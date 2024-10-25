---
UID: NS:dxva._DXVA_QMatrix_MJPEG
tech.root: display
title: DXVA_QMatrix_MJPEG
ms.date: 10/25/2024
targetos: Windows
description: Learn more about the DXVA_QMatrix_MJPEG structure.
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
req.typenames: DXVA_QMatrix_MJPEG, *LPDXVA_QMatrix_MJPEG
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
 - _DXVA_QMatrix_MJPEG
 - LPDXVA_QMatrix_MJPEG
 - DXVA_QMatrix_MJPEG
f1_keywords:
 - _DXVA_QMatrix_MJPEG
 - dxva/_DXVA_QMatrix_MJPEG
 - LPDXVA_QMatrix_MJPEG
 - dxva/LPDXVA_QMatrix_MJPEG
 - DXVA_QMatrix_MJPEG
 - dxva/DXVA_QMatrix_MJPEG
dev_langs:
 - c++
helpviewer_keywords:
 - _DXVA_QMatrix_MJPEG
---

## -description

The **DXVA_QMatrix_MJPEG** structure provides the quantization table of a compressed picture for MJPEG video decoding.

## -struct-fields

### -field quantvals[4]

Array for each quantization table slot *i*, containing an array of 64 entries *j*. Each entry *i* specifies 64 entries *j*, where each is a quantization step parameter for each coefficient. This array is filled directly from the DQT marker of the input MJPEG bitstream. The order of entries is the same as defined in the standard JPEG DQT marker: zig-zag scan order. All values are stored in 16-bit WORDs even if the table only specifies 8-bit values (Pq = 0).  If a quantization table is not present all entries will be initialized to zero.  The exact quantization table used for a particular component of a picture shall be read from the picture parameters structure field: quantizationTableSelector.

## -remarks

This structure is used for MJPEG video coding when the buffer type is [**D3D12_VIDEO_DECODE_ARGUMENT_TYPE_INVERSE_QUANTIZATION_MATRIX**](/windows/win32/api/d3d12video/ne-d3d12video-d3d12_video_decode_argument_type) in D3D12 and [**D3D11_VIDEO_DECODER_BUFFER_INVERSE_QUANTIZATION_MATRIX**](/windows/win32/api/d3d11/ne-d3d11-d3d11_video_decoder_buffer_type) in D3D11.

If **DXVA_QMatrix_MJPEG** is left unspecified by the host, the accelerator shall use the default quantization table as specified in Annex K of the JPEG specification.

## -see-also

[**D3D12_VIDEO_DECODE_ARGUMENT_TYPE**](/windows/win32/api/d3d12video/ne-d3d12video-d3d12_video_decode_argument_type)

[**D3D11_VIDEO_DECODER_BUFFER_TYPE**](/windows/win32/api/d3d11/ne-d3d11-d3d11_video_decoder_buffer_type)
