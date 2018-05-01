---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION
title: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION
author: windows-driver-content
description: Sets private state data for a video processor from an application.
old-location: display\videoprocessorsetoutputextension.htm
old-project: display
ms.assetid: 040aa673-4b80-4e89-a58d-f298936537cd
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION, PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION callback, d3d10umddi/pfnVideoProcessorSetOutputExtension, display.videoprocessorsetoutputextension, pfnVideoProcessorSetOutputExtension, pfnVideoProcessorSetOutputExtension callback function [Display Devices]
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
-	pfnVideoProcessorSetOutputExtension
product: Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION callback function


## -description


Sets private state data for a video processor from an application.


## -parameters




### -param Arg1


### -param Arg2


### -param *








### -param Arg3


#### - DataSize [in]

The size, in bytes, of the private state data in the buffer referenced by the <i>pData</i> parameter.


#### - hDevice [in]

A handle to the display device (graphics context).




#### - hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a> function. 




#### - pData [in]

A pointer to a buffer that contains the private state data. 



<div class="alert"><b>Note</b>  The Direct3D runtime does not validate the private state data in the buffer before it calls the  <b>VideoProcessorSetOutputExtension</b> function</div>
<div> </div>

#### - pGuid [in]

A pointer to a GUID that identifies the private state data. The meaning of this GUID is defined by the graphics driver.




## -returns



<b>VideoProcessorSetOutputExtension</b> returns one of the following values:

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
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Memory was not available to complete the operation.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a>
 

 

