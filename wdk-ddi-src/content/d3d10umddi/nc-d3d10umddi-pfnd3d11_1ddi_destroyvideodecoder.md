---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYVIDEODECODER
title: PFND3D11_1DDI_DESTROYVIDEODECODER (d3d10umddi.h)
description: Releases resources for the video decoder object that were created through a call to the CreateVideoDecoder function.
old-location: display\destroyvideodecoder.htm
ms.assetid: 541f4c9b-3193-46a8-9979-74456168988e
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_DESTROYVIDEODECODER callback function"]
ms.keywords: PFND3D11_1DDI_DESTROYVIDEODECODER, PFND3D11_1DDI_DESTROYVIDEODECODER callback, d3d10umddi/pfnDestroyVideoDecoder, display.destroyvideodecoder, pfnDestroyVideoDecoder, pfnDestroyVideoDecoder callback function [Display Devices]
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
 - PFND3D11_1DDI_DESTROYVIDEODECODER
 - d3d10umddi/PFND3D11_1DDI_DESTROYVIDEODECODER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnDestroyVideoDecoder
---

# PFND3D11_1DDI_DESTROYVIDEODECODER callback function


## -description

Releases resources for the video decoder object that were created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder">CreateVideoDecoder</a> function.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hDecoder* [in]

A handle to the driver's private data for the video decoder object. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder">CreateVideoDecoder</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder">CreateVideoDecoder</a>

