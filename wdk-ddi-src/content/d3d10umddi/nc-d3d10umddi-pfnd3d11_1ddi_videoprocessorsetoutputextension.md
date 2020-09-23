---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION
title: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION (d3d10umddi.h)
description: Sets private state data for a video processor from an application.
old-location: display\videoprocessorsetoutputextension.htm
ms.assetid: 040aa673-4b80-4e89-a58d-f298936537cd
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION callback function"]
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION, PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION callback, d3d10umddi/pfnVideoProcessorSetOutputExtension, display.videoprocessorsetoutputextension, pfnVideoProcessorSetOutputExtension, pfnVideoProcessorSetOutputExtension callback function [Display Devices]
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
 - PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION
 - d3d10umddi/PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnVideoProcessorSetOutputExtension
---

# PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION callback function


## -description

Sets private state data for a video processor from an application.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

### -param Arg3

*pGuid* [in]

A pointer to a GUID that identifies the private state data. The meaning of this GUID is defined by the graphics driver.

### -param Arg4

*DataSize* [in]

The size, in bytes, of the private state data in the buffer referenced by the <i>pData</i> parameter.

### -param Arg5

*pData* [in, out]

A pointer to a buffer that contains the private state data. 



<div class="alert"><b>Note</b>  The Direct3D runtime does not validate the private state data in the buffer before it calls the  <b>VideoProcessorSetOutputExtension</b> function</div>
<div> </div>

## -returns

<b>VideoProcessorSetOutputExtension</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The private state data was set successfully.|
|D3DDDIERR_DEVICEREMOVED|The graphics adapter was removed.|
|E_FAIL|The display miniport driver cannot set the requested private state data for the video processor.|
|E_OUTOFMEMORY|Memory was not available to complete the operation.|

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>