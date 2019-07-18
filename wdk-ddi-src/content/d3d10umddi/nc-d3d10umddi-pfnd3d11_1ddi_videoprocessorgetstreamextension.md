---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORGETSTREAMEXTENSION
title: PFND3D11_1DDI_VIDEOPROCESSORGETSTREAMEXTENSION (d3d10umddi.h)
description: Returns the private state data for a video processor stream to an application.
old-location: display\videoprocessorgetstreamextension.htm
ms.assetid: e2c91e9c-f8ab-48ba-b98a-332cb0ac7077
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORGETSTREAMEXTENSION, PFND3D11_1DDI_VIDEOPROCESSORGETSTREAMEXTENSION callback, d3d10umddi/pfnVideoProcessorGetStreamExtension, display.videoprocessorgetstreamextension, pfnVideoProcessorGetStreamExtension, pfnVideoProcessorGetStreamExtension callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d10umddi/pfnVideoProcessorGetStreamExtension"
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
- pfnVideoProcessorGetStreamExtension
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORGETSTREAMEXTENSION callback function


## -description


Returns the private state data for a video processor stream to an application.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

### -param Arg3

*StreamIndex* [in]

The zero-based index of the input stream.

### -param *

*pGuid* [in]

A pointer to a GUID that identifies the private state data. The meaning of this GUID is defined by the graphics driver.







### -param Arg4

*DataSize* [in]

The size, in bytes, of the private state data in the buffer referenced by the <i>pData</i> parameter.

### -param *

*pData* [in, out]

A pointer to a buffer that contains the private state data. 





## -returns



<b>VideoProcessorGetStreamExtension</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The private state data was returned successfully.|
|D3DDDIERR_DEVICEREMOVED|The graphics adapter was removed.|
|E_FAIL|The display miniport driver cannot set the requested private state data for the video processor.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
 
## -remarks



The Microsoft Direct3D runtime does not validate any parameter data before it calls the  <b>VideoProcessorGetStreamExtension</b> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>
 

 

