---
UID: NF:dxapi.DxApi
title: DxApi function (dxapi.h)
description: The DxApi function accepts commands from the hardware decoder's video capture driver to access the DxApi interface functions that are implemented in a video miniport driver.
old-location: display\dxapi.htm
tech.root: display
ms.assetid: c4b38376-b54f-4fbb-b305-5951a1ea76a1
ms.date: 05/10/2018
ms.keywords: DxApi, DxApi function [Display Devices], ddfncs_b76158a1-30ff-4874-b527-a201c5a67fc5.xml, display.dxapi, dxapi/DxApi
ms.topic: function
req.header: dxapi.h
req.include-header: Ddkmapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Dxapi.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Dxapi.lib
- Dxapi.dll
api_name:
- DxApi
product:
- Windows
targetos: Windows
req.typenames: 
---

# DxApi function


## -description


The <b>DxApi</b> function accepts commands from the hardware decoder's video capture driver to access the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">DxApi interface functions</a> that are implemented in a <a href="https://docs.microsoft.com/windows-hardware/drivers/display/video-miniport-drivers-in-the-windows-2000-display-driver-model">video miniport driver</a>.


## -parameters




### -param dwFunctionNum

Indicates the behavior of the <b>DxApi</b> function (function identifier). See the Remarks section for the list of function identifiers.


### -param lpvInBuffer

Points to the input buffer.


### -param cbInBuffer

Indicates the size in bytes of the input buffer.


### -param lpvOutBuffer

Points to the output buffer.


### -param cbOutBuffer

Indicates the size in bytes of the output buffer.


## -returns



<b>DxApi</b> returns the number of bytes actually written to the output buffer.




## -remarks



<b>DxApi</b> accepts a function identifier (<i>dwFunctionNum</i>), an input buffer (<i>lpvInBuffer</i>) and its size (<i>cbInBuffer</i>), and an output buffer (<i>lpvOutBuffer</i>) and its size (<i>cbOutBuffer</i>). The behavior of the function and the size and format of the input and output buffers depend on the specified function identifier. The return value is the number of actual bytes written into the output buffer.

The following function identifiers are defined for the <b>DxApi</b> function in the <i>ddkmapi.h</i> header file: 


<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550599(v=vs.85)">DD_DXAPI_ADDVPCAPTUREBUFFER</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550606(v=vs.85)">DD_DXAPI_CLOSEHANDLE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550612(v=vs.85)">DD_DXAPI_FLIP_OVERLAY</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550618(v=vs.85)">DD_DXAPI_FLIP_VP</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550622(v=vs.85)">DD_DXAPI_FLUSHVPCAPTUREBUFFERS</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550642(v=vs.85)">DD_DXAPI_GET_CURRENT_VP_AUTOFLIP_SURFACE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550650(v=vs.85)">DD_DXAPI_GET_LAST_VP_AUTOFLIP_SURFACE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550660(v=vs.85)">DD_DXAPI_GET_POLARITY</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550673(v=vs.85)">DD_DXAPI_GET_SURFACE_STATE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550686(v=vs.85)">DD_DXAPI_GET_VP_FIELD_NUMBER</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550629(v=vs.85)">DD_DXAPI_GETKERNELCAPS</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550637(v=vs.85)">DD_DXAPI_GETVERSIONNUMBER</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550695(v=vs.85)">DD_DXAPI_LOCK</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550702(v=vs.85)">DD_DXAPI_OPENDIRECTDRAW</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550711(v=vs.85)">DD_DXAPI_OPENSURFACE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551498(v=vs.85)">DD_DXAPI_OPENVIDEOPORT</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551500(v=vs.85)">DD_DXAPI_OPENVPCAPTUREDEVICE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551502(v=vs.85)">DD_DXAPI_REGISTER_CALLBACK</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551504(v=vs.85)">DD_DXAPI_SET_SURFACE_STATE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551507(v=vs.85)">DD_DXAPI_SET_VP_FIELD_NUMBER</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551510(v=vs.85)">DD_DXAPI_SET_VP_SKIP_FIELD</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551514(v=vs.85)">DD_DXAPI_UNREGISTER_CALLBACK</a>





## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550599(v=vs.85)">DD_DXAPI_ADDVPCAPTUREBUFFER</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550606(v=vs.85)">DD_DXAPI_CLOSEHANDLE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550612(v=vs.85)">DD_DXAPI_FLIP_OVERLAY</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550618(v=vs.85)">DD_DXAPI_FLIP_VP</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550622(v=vs.85)">DD_DXAPI_FLUSHVPCAPTUREBUFFERS</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550629(v=vs.85)">DD_DXAPI_GETKERNELCAPS</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550637(v=vs.85)">DD_DXAPI_GETVERSIONNUMBER</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550642(v=vs.85)">DD_DXAPI_GET_CURRENT_VP_AUTOFLIP_SURFACE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550650(v=vs.85)">DD_DXAPI_GET_LAST_VP_AUTOFLIP_SURFACE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550660(v=vs.85)">DD_DXAPI_GET_POLARITY</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550673(v=vs.85)">DD_DXAPI_GET_SURFACE_STATE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550686(v=vs.85)">DD_DXAPI_GET_VP_FIELD_NUMBER</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550695(v=vs.85)">DD_DXAPI_LOCK</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550702(v=vs.85)">DD_DXAPI_OPENDIRECTDRAW</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550711(v=vs.85)">DD_DXAPI_OPENSURFACE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551498(v=vs.85)">DD_DXAPI_OPENVIDEOPORT</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551500(v=vs.85)">DD_DXAPI_OPENVPCAPTUREDEVICE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551502(v=vs.85)">DD_DXAPI_REGISTER_CALLBACK</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551504(v=vs.85)">DD_DXAPI_SET_SURFACE_STATE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551507(v=vs.85)">DD_DXAPI_SET_VP_FIELD_NUMBER</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551510(v=vs.85)">DD_DXAPI_SET_VP_SKIP_FIELD</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551514(v=vs.85)">DD_DXAPI_UNREGISTER_CALLBACK</a>
 

 

