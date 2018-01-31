---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION
title: PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION
author: windows-driver-content
description: Returns private state data from a video processor to an application.
old-location: display\videoprocessorgetoutputextension.htm
old-project: display
ms.assetid: 16f314f7-a54b-4c79-9cd6-1472ed454bbe
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.videoprocessorgetoutputextension, pfnVideoProcessorGetOutputExtension callback function [Display Devices], pfnVideoProcessorGetOutputExtension, PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION, PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION, d3d10umddi/pfnVideoProcessorGetOutputExtension
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	pfnVideoProcessorGetOutputExtension
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION callback


## -description


Returns private state data from a video processor to an application.


## -prototype


````
PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION pfnVideoProcessorGetOutputExtension;

HRESULT APIENTRY* pfnVideoProcessorGetOutputExtension(
  _In_          D3D10DDI_HDEVICE           hDevice,
  _In_          D3D11_1DDI_HVIDEOPROCESSOR hVideoProcessor,
  _In_    const GUID                       *pGuid,
  _In_          UINT                       DataSize,
  _Inout_       void                       *pData
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param D3D11_1DDI_HVIDEOPROCESSOR



### -param *






### -param UINT



#### - hDevice [in]

A handle to the display device (graphics context).




#### - hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a> function. 




#### - pGuid [in]

A pointer to a GUID that identifies the private state data. The meaning of this GUID is defined by the graphics driver.




#### - DataSize [in]

The size, in bytes, of the private state data in the buffer referenced by the <i>pData</i> parameter.


#### - pData [in, out]

A pointer to a buffer that receives the private state data. 




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


The Microsoft Direct3D runtime does not validate any parameter data before it calls the  <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputextension.md">VideoProcessorSetOutputExtension</a> function.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORGETOUTPUTEXTENSION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

