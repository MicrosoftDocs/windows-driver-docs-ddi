---
UID: NC:d3dumddi.PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR
title: PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR (d3dumddi.h)
description: The CreateVideoProcessor function creates a Microsoft DirectX Video Acceleration (DirectX VA) video processor that is used to process high-definition video.
old-location: display\createvideoprocessor.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR callback function"]
ms.keywords: CreateVideoProcessor, CreateVideoProcessor callback function [Display Devices], PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR, PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR callback, UserModeDisplayDriver_Functions_ce6a0d51-9da3-43d9-ac23-c2e250ca4cfa.xml, d3dumddi/CreateVideoProcessor, display.createvideoprocessor
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateVideoProcessor is supported beginning with the Windows 7 operating system.
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
req.typenames: 
f1_keywords:
 - PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR
 - d3dumddi/PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - CreateVideoProcessor
product:
 - Windows
---

# PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR callback function


## -description

The <b>CreateVideoProcessor</b> function creates a Microsoft DirectX Video Acceleration (DirectX VA) video processor that is used to process high-definition video.

## -parameters

### -param Arg1

### -param Arg2

*hDevice* [in]

A handle to the display device (graphics context).


*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_dxvahd_createvideoprocessor">D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR</a> structure. On input, contains information that the driver can use. On output, the driver specifies information that the Microsoft Direct3D runtime can use.

## -returns

<b>CreateVideoProcessor</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The video processor is successfully created.|
|E_OUTOFMEMORY|CreateVideoProcessor could not allocate the required memory for it to complete.|

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_dxvahd_createvideoprocessor">D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_destroyvideoprocessor">DestroyVideoProcessor</a>
