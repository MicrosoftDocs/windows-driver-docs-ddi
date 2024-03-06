---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEODECODER_0072
title: PFND3D12DDI_CREATEVIDEODECODER_0072 (d3d12umddi.h)
description: The PFND3D12DDI_CREATEVIDEODECODER_0072 callback function creates a video decoder.
ms.date: 02/02/2022
keywords: ["PFND3D12DDI_CREATEVIDEODECODER_0072 callback function"]
ms.keywords: PFND3D12DDI_CREATEVIDEODECODER_0072, PFND3D12DDI_CREATEVIDEODECODER_0072 callback, PFND3D12DDI_CREATEVIDEODECODER_0072 callback function [Display Devices], d3d12umddi/PFND3D12DDI_CREATEVIDEODECODER_0072, display.pfnd3d12ddi_createvideodecoder_0072
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 2004 (WDDM 2.8)
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
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D12DDI_CREATEVIDEODECODER_0072
 - d3d12umddi/PFND3D12DDI_CREATEVIDEODECODER_0072
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATEVIDEODECODER_0072
---

# PFND3D12DDI_CREATEVIDEODECODER_0072 callback function

## -description

A client driver's **PFND3D12DDI_CREATEVIDEODECODER_0072** callback function creates a video decoder.

## -parameters

### -param hDrvDevice

[in] Handle for the D3D12 device.

### -param pArgs

[in] Pointer to a [**D3D12DDIARG_CREATE_VIDEO_DECODER_0072**](ns-d3d12umddi-d3d12ddiarg_create_video_decoder_0072.md) structure with arguments to create this video decoder object.

### -param hDrvVideoDecoder

[out] Handle to the created video decoder object.

## -returns

Returns an [**HRESULT**](/windows-hardware/drivers/debugger/hresult-values) value.

## -remarks

See the [D3D Video Protected Resource Support Specification](https://microsoft.github.io/DirectX-Specs/d3d/D3D12_Video_ProtectedResourceSupport.html) for more information.

## -see-also

[**D3D12DDIARG_CREATE_VIDEO_DECODER_0072**](ns-d3d12umddi-d3d12ddiarg_create_video_decoder_0072.md)
