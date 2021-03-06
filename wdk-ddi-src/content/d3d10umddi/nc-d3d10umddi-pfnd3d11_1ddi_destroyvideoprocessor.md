---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYVIDEOPROCESSOR
title: PFND3D11_1DDI_DESTROYVIDEOPROCESSOR (d3d10umddi.h)
description: Releases resources for the video processor object that were created through a call to the CreateVideoProcessor function.
old-location: display\destroyvideoprocessor1.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_DESTROYVIDEOPROCESSOR callback function"]
ms.keywords: PFND3D11_1DDI_DESTROYVIDEOPROCESSOR, PFND3D11_1DDI_DESTROYVIDEOPROCESSOR callback, d3d10umddi/pfnDestroyVideoProcessor, display.destroyvideoprocessor1, display.pfndestroyvideoprocessor1, pfnDestroyVideoProcessor, pfnDestroyVideoProcessor callback function [Display Devices]
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
 - PFND3D11_1DDI_DESTROYVIDEOPROCESSOR
 - d3d10umddi/PFND3D11_1DDI_DESTROYVIDEOPROCESSOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_DESTROYVIDEOPROCESSOR
---

# PFND3D11_1DDI_DESTROYVIDEOPROCESSOR callback function


## -description

Releases resources for the video processor object that were created through a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

## -parameters

### -param unnamedParam1

*hDevice* [in]

A handle to the display device (graphics context).

### -param unnamedParam2

*hProcessor* [in]

A handle to the driver's private data for the video processor object. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>

