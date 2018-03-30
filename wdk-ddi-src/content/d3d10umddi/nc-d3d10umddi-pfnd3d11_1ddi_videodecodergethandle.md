---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEODECODERGETHANDLE
title: PFND3D11_1DDI_VIDEODECODERGETHANDLE
author: windows-driver-content
description: Returns the driver's handle for a video decoder that can be used by the application to configure content protection.
old-location: display\videodecodergethandle.htm
old-project: display
ms.assetid: 05c16416-d48c-44ce-b025-d62d763682bc
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11_1DDI_VIDEODECODERGETHANDLE, d3d10umddi/pfnVideoDecoderGetHandle, display.videodecodergethandle, pfnVideoDecoderGetHandle, pfnVideoDecoderGetHandle callback function [Display Devices]
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
-	pfnVideoDecoderGetHandle
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_VIDEODECODERGETHANDLE callback


## -description


Returns the driver's handle for a video decoder that can be used by the application  to configure content protection.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param Arg1


### -param *pContentProtectionHandle [out]

A pointer to the handle.


#### - hDecoder [in]

A handle to the video decoder object that was created through a call to the <a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a> function.




## -returns



<b>VideoDecoderGetHandle</b> returns one of the following values:

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
The handle was returned successfully.

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
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Memory was not available to complete the operation.

</td>
</tr>
</table>
 




## -remarks



The <b>VideoDecoderGetHandle</b> function returns a driver handle for the video decoder. This handle can be used by the application to associate the decoder with a cryptographic session over the authenticated channel.

This function allows the driver to define its own handle to its state data for the video decoder. This bypasses any handle mapping that may be performed by the Microsoft Direct3D runtime.

<div class="alert"><b>Note</b>  Drivers can return the same handle in the <i>pHandle</i> parameter that was passed  in the <i>hDecoder</i> parameter.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406330">D3D11_1DDIARG_VIDEODECODEREXTENSION</a>
 

 

