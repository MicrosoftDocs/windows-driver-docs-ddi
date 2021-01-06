---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0072
title: PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0072 (d3d12umddi.h)
description: Used to calculate the size of a video decoder.
ms.date: 03/24/2020
keywords: ["PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0072 callback function"]
ms.keywords: PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0072, PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0072 entry, PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0072 entry point [Display Devices], d3d12umddi/PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0072, display.pfnd3d12ddi_calcprivatevideodeCODERSIZE_0072
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
 - PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0072
 - d3d12umddi/PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0072
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0072
product:
 - Windows
---

# PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0072 callback function


## -description

Used to calculate the size of a video decoder. The D3D runtime allocates memory for storing the driver's CPU object representing the video decoder.

## -parameters

### -param hDrvDevice

The hardware device being processed.

### -param pArgs

[in] Pointer to a [**D3D12DDIARG_CREATE_VIDEO_DECODER_0072**](ns-d3d12umddi-d3d12ddiarg_create_video_decoder_0072.md) structure with arguments used to create a video decoder.

## -returns

Returns the size of the video decoder in bytes.

## -remarks

The runtime allocates memory for storing the driver CPU object that represents the video decoder.  This method is used to calculate the driver object size.

See the [D3D Video Protected Resource Support Specification](https://microsoft.github.io/DirectX-Specs/d3d/D3D12_Video_ProtectedResourceSupport.html) for more information.

## -see-also

[**D3D12DDIARG_CREATE_VIDEO_DECODER_0072**](ns-d3d12umddi-d3d12ddiarg_create_video_decoder_0072.md)

