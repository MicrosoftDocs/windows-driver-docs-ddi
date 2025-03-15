---
UID: NS:dxva._DXVA_PicParams_MJPEG
tech.root: display
title: DXVA_PicParams_MJPEG
ms.date: 10/25/2024
targetos: Windows
description: Learn more about the DXVA_PicParams_MJPEG structure.
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
req.typenames: DXVA_PicParams_MJPEG, *LPDXVA_PicParams_MJPEG
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
 - _DXVA_PicParams_MJPEG
 - LPDXVA_PicParams_MJPEG
 - DXVA_PicParams_MJPEG
f1_keywords:
 - _DXVA_PicParams_MJPEG
 - dxva/_DXVA_PicParams_MJPEG
 - LPDXVA_PicParams_MJPEG
 - dxva/LPDXVA_PicParams_MJPEG
 - DXVA_PicParams_MJPEG
 - dxva/DXVA_PicParams_MJPEG
dev_langs:
 - c++
helpviewer_keywords:
 - _DXVA_PicParams_MJPEG
---

## -description

The **DXVA_PicParams_MJPEG** structure provides the picture-level parameters of a compressed picture for MJPEG video decoding.

## -struct-fields

### -field width

The coded width of the current frame. This value corresponds to the Frame Header value X from the JPEG specification. It must be a multiple of 8 to align with JPEG's macroblock size.

### -field height

The coded height of the current frame. This value corresponds to the Frame Header value Y from the JPEG specification. It must be a multiple of 8 to align with JPEG's macroblock size.

### -field numComponents

The number of color components in the image data. The allowed values are restricted by the profile value. This value corresponds to the Frame Header value Nf (number of image components in frame) from the JPEG specification.

### -field bitDepth

The precision in bits for the samples in the components of the frame. The allowed values are restricted by the profile value. This value corresponds to the Frame Header value P (sample precision) from the JPEG specification.

### -field reserved16Bits

Reserved for future use; set to zero.

### -field quantizationTableSelector[4]

Array of four values used to select the quantization tables for each component. Each value corresponds to the value of Tq*i* from the specification. The number of quantization tables referenced is limited based on the profile value. Components are always in the order: Y,Cb,Cr,A.

### -field scanOffset[4]

Locates the compressed bitstream data for each scan *i* in the image. Specifically, this is the byte offset from the start of the bitstream buffer of the SOS marker (inclusive) from the specification.

### -field scanSize[4]

Number of bytes in the bitstream data buffer that are associated with each scan *i*.

### -field componentIdentifier[4]

For each of the four components in the image, specifies an identifier for the component that is used by the scan header (SOS) to identify the component. This value corresponds to the Frame Header value C*i* from the JPEG specification. Components are always in the order: Y,Cb,Cr,A.

### -field restartInterval

Restart interval for the JPEG decoder.

### -field reserved16Bits2

Reserved for future use and alignment.

### -field reserved32Bits

Reserved for future use and alignment.

### -field statusReportFeedbackNumber

Arbitrary number set by the host decoder to use as a tag in the status report feedback data. The value should not be equal to 0 and should be different in each call to Execute.

## -remarks

This structure is used for MJPEG video coding when the buffer type is [**D3D12_VIDEO_DECODE_ARGUMENT_TYPE_PICTURE_PARAMETERS**](/windows/win32/api/d3d12video/ne-d3d12video-d3d12_video_decode_argument_type) in D3D12 and [**D3D11_VIDEO_DECODER_BUFFER_PICTURE_PARAMETERS**](/windows/win32/api/d3d11/ne-d3d11-d3d11_video_decoder_buffer_type) in D3D11.

In DXVA, components always have the following ordering: Y,Cb,Cr,A.

## -see-also

[**D3D12_VIDEO_DECODE_ARGUMENT_TYPE**](/windows/win32/api/d3d12video/ne-d3d12video-d3d12_video_decode_argument_type)

[**D3D11_VIDEO_DECODER_BUFFER_TYPE**](/windows/win32/api/d3d11/ne-d3d11-d3d11_video_decoder_buffer_type)
