---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0072
title: PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0072 (d3d12umddi.h)
description: PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0072 is used to calculate the size of a video decoder heap.
ms.assetid: 9ca52fa7-9a21-48a0-ae94-160eed795c78
ms.date: 03/24/2020
keywords: ["PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0072 callback function"]
ms.keywords: PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0072, PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0072 entry, PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0072 entry point [Display Devices], d3d12umddi/PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0072, display.pfnd3d12ddi_calcprivatevideodecoderheapsize_0072
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
 - PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0072
 - d3d12umddi/PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0072
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0072
product:
 - Windows
---

# PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0072 callback function


## -description

**PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0072** is used to calculate the size of a video decoder heap. The D3D runtime allocates memory for storing the driver's CPU object representing the video decoder heap.

## -parameters

### -param hDrvDevice

Handle to the hardware device being processed.

### -param pArgs

[in] Pointer to a [**D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0072**](ns-d3d12umddi-d3d12ddiarg_create_video_decoder_heap_0072.md) structure with arguments used to create a video decoder heap.

## -returns

Returns the size of the heap in bytes.

## -remarks

See the [Video Protected Resource Support specification](https://microsoft.github.io/DirectX-Specs/d3d/D3D12_Video_ProtectedResourceSupport.html) for more information.

## -see-also

[**D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0072**](ns-d3d12umddi-d3d12ddiarg_create_video_decoder_heap_0072.md)

