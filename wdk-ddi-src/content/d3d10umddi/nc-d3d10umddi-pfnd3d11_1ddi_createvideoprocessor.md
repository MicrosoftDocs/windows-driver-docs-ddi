---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEVIDEOPROCESSOR
title: PFND3D11_1DDI_CREATEVIDEOPROCESSOR (d3d10umddi.h)
description: Creates a video processor object.
old-location: display\createvideoprocessor1.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_CREATEVIDEOPROCESSOR callback function"]
ms.keywords: CreateVideoProcessor, CreateVideoProcessor callback function [Display Devices], PFND3D11_1DDI_CREATEVIDEOPROCESSOR, PFND3D11_1DDI_CREATEVIDEOPROCESSOR callback, d3d10umddi/CreateVideoProcessor, display.createvideoprocessor1, display.pfncreatevideoprocessor1
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
 - PFND3D11_1DDI_CREATEVIDEOPROCESSOR
 - d3d10umddi/PFND3D11_1DDI_CREATEVIDEOPROCESSOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - CreateVideoProcessor
product:
 - Windows
---

# PFND3D11_1DDI_CREATEVIDEOPROCESSOR callback function


## -description

Creates a video processor object.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessor">D3D11_1DDIARG_CREATEVIDEOPROCESSOR</a> structure. This structure specifies the attributes of the video processor object to be created.

### -param Arg3

*hVideoProcessor* [in]

A handle to the driver's private data for the video processor object.

### -param Arg4

*hRTVideoProcessor* [in]

A handle to the video processor object that the driver should use when it calls back into the Direct3D runtime.

## -returns

<b>CreateVideoProcessor</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The video processor object was created successfully.|
|D3DDDIERR_DEVICEREMOVED|The graphics adapter was removed.|
|E_OUTOFMEMORY|Memory was not available to complete the operation.|

## -remarks

The <i>CreateVideoProcessor</i> function creates a video processor object that contains specific capabilities and state.  Multiple video processor objects can exist at the same time, each with its own unique state.

The Direct3D runtime calls <i>CreateVideoProcessor</i> after it has called the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorsize">CalcPrivateVideoProcessorSize</a>   to determine the size in bytes for the private data that the driver requires for the video processor object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video processor object.

When the runtime  calls <i>CreateVideoProcessor</i>, it passes the handle to the private data memory in the <i>hProcessor</i> parameter. This handle is actually a pointer to the memory.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorsize">CalcPrivateVideoProcessorSize</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessor">D3D11_1DDIARG_CREATEVIDEOPROCESSOR</a>
