---
UID: NS:dxva._DXVA_HuffmanTable_MJPEG
tech.root: display
title: DXVA_HuffmanTable_MJPEG
ms.date: 10/25/2024
targetos: Windows
description: Learn more about the DXVA_HuffmanTable_MJPEG structure.
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
req.typenames: DXVA_HuffmanTable_MJPEG, *LPDXVA_HuffmanTable_MJPEG
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
 - _DXVA_HuffmanTable_MJPEG
 - LPDXVA_HuffmanTable_MJPEG
 - DXVA_HuffmanTable_MJPEG
f1_keywords:
 - _DXVA_HuffmanTable_MJPEG
 - dxva/_DXVA_HuffmanTable_MJPEG
 - LPDXVA_HuffmanTable_MJPEG
 - dxva/LPDXVA_HuffmanTable_MJPEG
 - DXVA_HuffmanTable_MJPEG
 - dxva/DXVA_HuffmanTable_MJPEG
dev_langs:
 - c++
helpviewer_keywords:
 - _DXVA_HuffmanTable_MJPEG
---

## -description

The **DXVA_HuffmanTable_MJPEG** structure provides the Huffman table of a compressed picture for MJPEG video decoding.

## -struct-fields

### -field bits_ac[4]

The **bits_ac[j][i]** member specifies the number of Huffman codes of length *i* for Huffman table slot *j* for AC class tables. This value is the same as the L*i* parameter of the DHT marker from the specification.

### -field table_ac[4]

The **table_ac[j][i]** member specifies the value associated with each Huffman code *j* for Huffman table slot I for AC class tables. This corresponds to the V*i,j* parameter from the DHT marker of the specification.

### -field bits_dc[4]

The **bits_dc[j][i]** member specifies the number of Huffman codes of length *i* for Huffman table slot *j* for DC class tables.  This value is the same as the L*i* parameter of the DHT marker from the specification.

### -field table_dc[4]

The **table_dc[j][i]** member specifies the value associated with each Huffman code *j* for Huffman table slot I for DC class tables. This corresponds to the V*i,j* parameter from the DHT marker of the specification.

## -remarks

This structure is used for MJPEG video coding when the buffer type is [**D3D12_VIDEO_DECODE_ARGUMENT_TYPE_HUFFMAN_TABLE**](/windows/win32/api/d3d12video/ne-d3d12video-d3d12_video_decode_argument_type) in D3D12 and [**D3D11_VIDEO_DECODER_BUFFER_HUFFMAN_TABLE**](/windows/win32/api/d3d11/ne-d3d11-d3d11_video_decoder_buffer_type) in D3D11.

If **DXVA_HuffmanTable_MJPEG** is left unspecified by the host, the accelerator shall use the default quantization table as specified in Annex K of the JPEG specification.

## -see-also

[**D3D12_VIDEO_DECODE_ARGUMENT_TYPE**](/windows/win32/api/d3d12video/ne-d3d12video-d3d12_video_decode_argument_type)

[**D3D11_VIDEO_DECODER_BUFFER_TYPE**](/windows/win32/api/d3d11/ne-d3d11-d3d11_video_decoder_buffer_type)
