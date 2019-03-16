---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION (d3d10umddi.h)
description: Sets the private state data for a video processor stream from an application.
old-location: display\videoprocessorsetstreamextension.htm
ms.assetid: 380f7fbd-34aa-401b-a7dc-5d8b521f7948
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION callback, d3d10umddi/pfnVideoProcessorSetStreamExtension, display.videoprocessorsetstreamextension, pfnVideoProcessorSetStreamExtension, pfnVideoProcessorSetStreamExtension callback function [Display Devices]
ms.topic: callback
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
- pfnVideoProcessorSetStreamExtension
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION callback function


## -description


Sets the private state data for a video processor stream from an application.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a> function.

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



> [!NOTE]
> The Direct3D runtime does not validate the private state data in the buffer before it calls the  <b>VideoProcessorSetStreamExtension</b> function</div>
<div> </div>



## -returns



<b>VideoProcessorSetStreamExtension</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The private state data was set successfully.|
|D3DDDIERR_DEVICEREMOVED|The graphics adapter was removed.|
|E_FAIL|The display miniport driver cannot set the requested private state data for the video processor.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
 




## -see-also




<a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a>
 

 

