---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEODECODERHEAP_0072
title: PFND3D12DDI_CREATEVIDEODECODERHEAP_0072 (d3d12umddi.h)
description: PFND3D12DDI_CREATEVIDEODECODERHEAP_0072 is used to create a video decoder heap.
ms.assetid: 2795dd57-d76b-43db-a450-cd8cb5173aec
ms.date: 03/24/2020
keywords: ["PFND3D12DDI_CREATEVIDEODECODERHEAP_0072 callback function"]
ms.keywords: PFND3D12DDI_CREATEVIDEODECODERHEAP_0072, PFND3D12DDI_CREATEVIDEODECODERHEAP_0072  callback, PFND3D12DDI_CREATEVIDEODECODERHEAP_0072 callback function [Display Devices], d3d12umddi/PFND3D12DDI_CREATEVIDEODECODERHEAP_0072, display.pfnd3d12ddi_createvideodecoderheap_0072_
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 2004
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
 - "d3d12umddi/PFND3D12DDI_CREATEVIDEODECODERHEAP_0072"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATEVIDEODECODERHEAP_0072
product:
 - Windows
---

# PFND3D12DDI_CREATEVIDEODECODERHEAP_0072 callback function

## -description

**PFND3D12DDI_CREATEVIDEODECODERHEAP_0072** is used to create a video decoder heap.

## -parameters

### -param hDrvDevice

Handle to the hardware device being processed.

### -param Arg2

[in] Pointer to a [**D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0072**](ns-d3d12umddi-d3d12ddiarg_create_video_decoder_heap_0072.md) structure with the arguments used to create a video decoder heap.

### -param hDrvVideoDecoderHeap

Handle to the video decoder heap.

## -returns

Returns STATUS_SUCCESS if completed successfully.

## -remarks

See the [Video Protected Resource Support specification](https://microsoft.github.io/DirectX-Specs/d3d/D3D12_Video_ProtectedResourceSupport.html) for more information.

## -see-also

[**D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0072**](ns-d3d12umddi-d3d12ddiarg_create_video_decoder_heap_0072.md)
