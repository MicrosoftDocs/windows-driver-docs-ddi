---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION
title: PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION (d3d10umddi.h)
description: Returns private state data from a video processor to an application.
old-location: display\videoprocessorgetoutputextension.htm
ms.assetid: 16f314f7-a54b-4c79-9cd6-1472ed454bbe
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION, PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION callback, d3d10umddi/pfnVideoProcessorGetOutputExtension, display.videoprocessorgetoutputextension, pfnVideoProcessorGetOutputExtension, pfnVideoProcessorGetOutputExtension callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d10umddi/pfnVideoProcessorGetOutputExtension"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- pfnVideoProcessorGetOutputExtension
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION callback function


## -description


Returns private state data from a video processor to an application.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

### -param *

*pGuid* [in]

A pointer to a GUID that identifies the private state data. The meaning of this GUID is defined by the graphics driver.






### -param Arg3

*DataSize* [in]

The size, in bytes, of the private state data in the buffer referenced by the <i>pData</i> parameter.

### -param *

*pData* [in, out]

A pointer to a buffer that receives the private state data. 



## -returns



<b>VideoProcessorGetOutputExtension</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The private state data was returned successfully.|
|D3DDDIERR_DEVICEREMOVED|The graphics adapter was removed.|
|E_FAIL|The display miniport driver cannot return the requested private state data from the video processor.|
|E_OUTOFMEMORY|Memory was not available to complete the operation.|
 

## -remarks



The Microsoft Direct3D runtime does not validate any parameter data before it calls the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputextension">VideoProcessorSetOutputExtension</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>
 

 

