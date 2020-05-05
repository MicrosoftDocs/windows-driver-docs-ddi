---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_DECODER_0072
title: D3D12DDIARG_CREATE_VIDEO_DECODER_0072
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
ms.assetid: a0de7dff-c080-4607-95c8-66855b67c89f
tech.root: display
description: Structure used to create a video decoder.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDIARG_CREATE_VIDEO_DECODER_0072
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_CREATE_VIDEO_DECODER_0072
f1_keywords:
 - d3d12umddi/D3D12DDIARG_CREATE_VIDEO_DECODER_0072
dev_langs:
 - c++
---

## -description

Structure used to create a video decoder.

## -struct-fields

### -field NodeMask

Represents the set of nodes. For a single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.

### -field Configuration

The decode profile and bitstream encryption. See [**D3D12DDI_VIDEO_DECODE_CONFIGURATION**](ns-d3d12umddi-d3d12ddi_video_decode_configuration_0020.md).

### -field hDrvProtectedResourceSession

Handle to the protected resource session acquired at object creation time.

## -remarks

See the [D3D Video Protected Resource Support Specification](https://microsoft.github.io/DirectX-Specs/d3d/ProtectedResources.html) for more information.

## -see-also

[**D3D12DDI_VIDEO_DECODE_CONFIGURATION**](ns-d3d12umddi-d3d12ddi_video_decode_configuration_0020.md)

[**PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0072**](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideodecodersize_0072.md)

[**PFND3D12DDI_CREATEVIDEODECODER_0072**](nc-d3d12umddi-pfnd3d12ddi_createvideodecoder_0072.md)
