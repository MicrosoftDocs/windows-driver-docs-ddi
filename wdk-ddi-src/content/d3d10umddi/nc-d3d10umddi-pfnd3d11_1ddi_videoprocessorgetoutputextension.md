---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION
title: PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION
author: windows-driver-content
description: Returns private state data from a video processor to an application.
old-location: display\videoprocessorgetoutputextension.htm
old-project: display
ms.assetid: 16f314f7-a54b-4c79-9cd6-1472ed454bbe
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION, d3d10umddi/pfnVideoProcessorGetOutputExtension, display.videoprocessorgetoutputextension, pfnVideoProcessorGetOutputExtension, pfnVideoProcessorGetOutputExtension callback function [Display Devices]
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
-	pfnVideoProcessorGetOutputExtension
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION callback


## -description


Returns private state data from a video processor to an application.


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




#### - pData [in, out]

A pointer to a buffer that receives the private state data. 




#### - pGuid [in]

A pointer to a GUID that identifies the private state data. The meaning of this GUID is defined by the graphics driver.




## -returns



<b>VideoProcessorGetOutputExtension</b> returns one of the following values:

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
The private state data was returned successfully.

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

        The display miniport driver cannot return the requested private state data from the video processor.

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
 




## -remarks



The Microsoft Direct3D runtime does not validate any parameter data before it calls the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439786">VideoProcessorSetOutputExtension</a> function.




## -see-also




<a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a>
 

 

