---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT
tech.root: display
title: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT
ms.date: 12/09/2022
targetos: Windows
description: Learn more about the D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d10umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.target-type: 
req.typenames: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT
f1_keywords:
 - D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT
 - d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT
dev_langs:
 - c++
helpviewer_keywords:
 - D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT
---

## -description

**D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT** describes the video decoder down sample output format capabilities. The driver provides these capabilities when its [**PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES**](nc-d3d10umddi-pfnd3dwddm2_0ddi_queryvideocapabilities.md) function is called.

## -struct-fields

### -field DecodeProfile

[in] The decode profile for which capabilities are being queried.

### -field Format

[in] A [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format) value that specifies the output format.

### -field Supported

[out] The driver sets this value to TRUE if it supports the specified **Format** for the **DecodeProfile**; otherwise it sets this value to FALSE.

## -see-also

[**D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY**](ne-d3d10umddi-d3dwddm2_0ddi_video_capability_query.md)

[**PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES**](nc-d3d10umddi-pfnd3dwddm2_0ddi_queryvideocapabilities.md)
