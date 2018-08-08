---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION
author: windows-driver-content
description: Sets the private state data for a video processor stream from an application.
old-location: display\videoprocessorsetstreamextension.htm
tech.root: display
ms.assetid: 380f7fbd-34aa-401b-a7dc-5d8b521f7948
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION callback, d3d10umddi/pfnVideoProcessorSetStreamExtension, display.videoprocessorsetstreamextension, pfnVideoProcessorSetStreamExtension, pfnVideoProcessorSetStreamExtension callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	pfnVideoProcessorSetStreamExtension
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION callback function


## -description


Sets the private state data for a video processor stream from an application.


## -parameters




### -param Arg1


### -param Arg2


### -param Arg3


### -param *








### -param Arg4


#### - DataSize [in]

The size, in bytes, of the private state data in the buffer referenced by the <i>pData</i> parameter.


#### - StreamIndex [in]

The zero-based index of the input stream.


#### - hDevice [in]

A handle to the display device (graphics context).




#### - hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a> function. 




#### - pData [in]

A pointer to a buffer that contains the private state data. 



<div class="alert"><b>Note</b>  The Direct3D runtime does not validate the private state data in the buffer before it calls the  <b>VideoProcessorSetStreamExtension</b> function</div>
<div> </div>

#### - pGuid [in]

A pointer to a GUID that identifies the private state data. The meaning of this GUID is defined by the graphics driver.




## -returns



<b>VideoProcessorSetStreamExtension</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The private state data was set successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was removed.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">

        The display miniport driver cannot set the requested private state data for the video processor.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.


</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a>
 

 

