---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS
title: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS (d3d10umddi.h)
description: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS contains information describing the capabilities of the video decoder.
old-location: display\d3dwddm2_0ddi_video_capability_decoder_caps.htm
ms.date: 12/09/2022
keywords: ["D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS structure"]
ms.keywords: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS, D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS, display.d3dwddm2_0ddi_video_capability_decoder_caps
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
tech.root: display
req.typenames: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS
f1_keywords:
 - D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS
 - d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS
---

# D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS structure

## -description

**D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS** describes the capabilities of the video decoder. The driver provides these capabilities when its [**PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES**](nc-d3d10umddi-pfnd3dwddm2_0ddi_queryvideocapabilities.md) function is called.

## -struct-fields

### -field DecodeProfile

[in] The decode profile for which capabilities are being queried.

### -field SampleWidth

[in] The width in pixels of the video frame.

### -field SampleHeight

[in] The height in pixels of the video frame.

### -field FrameRate

[in] The frame rate of the video content.

### -field BitRate

[in] The bit rate of the video content.

### -field pCryptoType

[in] A pointer to a GUID that specifies the type of encryption algorithm. This field can have the following value.

| Value | Meaning |
| ----- | ------- |
| D3D11_1DDI_CRYPTO_TYPE_AES128_CTR | Queries whether the driver supports 128-bit Advanced Encryption Standard CTR mode (AES-CTR) block cipher encryption. |

### -field Caps

[out] Field in which the driver returns a bitwise OR of [**D3DWDDM2_0DDI_VIDEO_DECODER_CAPS**](ne-d3d10umddi-d3dwddm2_0ddi_video_decoder_caps.md) enumeration values that reflect the video decoder's capabilities.

## -see-also

[**D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY**](ne-d3d10umddi-d3dwddm2_0ddi_video_capability_query.md)

[**D3DWDDM2_0DDI_VIDEO_DECODER_CAPS**](ne-d3d10umddi-d3dwddm2_0ddi_video_decoder_caps.md)

[**PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES**](nc-d3d10umddi-pfnd3dwddm2_0ddi_queryvideocapabilities.md)
