---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEODECODEREXTENSION
title: PFND3D11_1DDI_VIDEODECODEREXTENSION
author: windows-driver-content
description: Performs an extended function for DirectX Video Acceleration (DXVA) decoding. This method enables extensions to the basic DXVA decoder functionality.
old-location: display\videodecoderextension.htm
old-project: display
ms.assetid: 0cfcc05a-77d7-4157-bd27-ba127afe3e92
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D11_1DDI_VIDEODECODEREXTENSION, d3d10umddi/pfnVideoDecoderExtension, display.videodecoderextension, pfnVideoDecoderExtension, pfnVideoDecoderExtension callback function [Display Devices]
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
-	pfnVideoDecoderExtension
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_VIDEODECODEREXTENSION callback


## -description


Performs an extended function for DirectX Video Acceleration (DXVA) decoding. This method enables extensions to the basic DXVA decoder functionality.




## -parameters




### -param Arg1


### -param Arg2


### -param *








#### - hDecoder [in]

A handle to the video decoder object that was created through a call to the <a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a> function.




#### - hDevice [in]

A handle to the display device (graphics context).




#### - pExtension [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406330">D3D11_1DDIARG_VIDEODECODEREXTENSION</a> structure that contains data for the extended function.




## -returns



<b>VideoDecoderExtension</b> returns one of the following values:

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
The extension was performed successfully.

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
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

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




<a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406330">D3D11_1DDIARG_VIDEODECODEREXTENSION</a>
 

 

