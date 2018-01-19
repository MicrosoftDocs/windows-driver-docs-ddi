---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION
title: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION
author: windows-driver-content
description: Sets private state data for a video processor from an application.
old-location: display\videoprocessorsetoutputextension.htm
old-project: display
ms.assetid: 040aa673-4b80-4e89-a58d-f298936537cd
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
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
req.alt-api: pfnVideoProcessorSetOutputExtension
req.alt-loc: D3d10umddi.h
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
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION callback



## -description
Sets private state data for a video processor from an application.



## -prototype

````
PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION pfnVideoProcessorSetOutputExtension;

HRESULT APIENTRY* pfnVideoProcessorSetOutputExtension(
  _In_       D3D10DDI_HDEVICE           hDevice,
  _In_       D3D11_1DDI_HVIDEOPROCESSOR hVideoProcessor,
  _In_ const GUID                       *pGuid,
  _In_       UINT                       DataSize,
  _In_       void                       *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).




### -param hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a> function. 




### -param pGuid [in]

A pointer to a GUID that identifies the private state data. The meaning of this GUID is defined by the graphics driver.




### -param DataSize [in]

The size, in bytes, of the private state data in the buffer referenced by the <i>pData</i> parameter.


### -param pData [in]

A pointer to a buffer that contains the private state data. 



<div class="alert"><b>Note</b>  The Direct3D runtime does not validate the private state data in the buffer before it calls the  <b>VideoProcessorSetOutputExtension</b> function</div>
<div> </div>

## -returns
<b>VideoProcessorSetOutputExtension</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The private state data was set successfully.
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>The graphics adapter was removed.

<dl>
<dt><b>E_FAIL</b></dt>
</dl>
        The display miniport driver cannot set the requested private state data for the video processor.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
        Memory was not available to complete the operation.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTEXTENSION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

