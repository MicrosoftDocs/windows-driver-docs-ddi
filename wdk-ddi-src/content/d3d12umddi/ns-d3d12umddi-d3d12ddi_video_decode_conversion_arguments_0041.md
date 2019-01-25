---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0041
title: D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0041 (d3d12umddi.h)
description: Specifies the arguments for decode output conversion.
ms.assetid: a7539a5e-e16b-48d9-b731-e55c2514ac66
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0041, D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0041,
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0041
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0041
product: 
- Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0041 structure

## -description

Specifies the arguments for decode output conversion.

## -struct-fields

### -field Enable

Indicates whether decode conversion should be used.

### -field hDrvReferenceTexture2D

If down sampling is enabled, the output at decode resolution, color space, and format may be required for future decode submissions.  If it is not needed, specify null.

### -field ReferenceSubresource

The subresource index to use of the *hDrvReferenceTexture2D* argument.

### -field OutputColorSpace

The target color space of the output.

### -field DecodeColorSpace

The source decoded color space before conversion.

### -field OutputWidth

The output width of before conversion.

### -field OutputHeight

The output height before conversion.

