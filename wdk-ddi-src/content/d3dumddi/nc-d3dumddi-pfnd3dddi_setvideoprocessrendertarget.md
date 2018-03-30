---
UID: NC:d3dumddi.PFND3DDDI_SETVIDEOPROCESSRENDERTARGET
title: PFND3DDDI_SETVIDEOPROCESSRENDERTARGET
author: windows-driver-content
description: The SetVideoProcessRenderTarget function sets the render target surface that is used for video processing.
old-location: display\setvideoprocessrendertarget.htm
old-project: display
ms.assetid: 8aa7e23e-f52e-4252-9f22-56ce523f6cba
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_SETVIDEOPROCESSRENDERTARGET, SetVideoProcessRenderTarget, SetVideoProcessRenderTarget callback function [Display Devices], UserModeDisplayDriver_Functions_8ce2d981-2c69-45e9-a2e2-eba9026be1a0.xml, d3dumddi/SetVideoProcessRenderTarget, display.setvideoprocessrendertarget
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	SetVideoProcessRenderTarget
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETVIDEOPROCESSRENDERTARGET callback


## -description


The <i>SetVideoProcessRenderTarget</i> function sets the render target surface that is used for video processing.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543372">D3DDDIARG_SETVIDEOPROCESSRENDERTARGET</a> structure that describes the render target surface that is used for video processing.


## -returns



<i>SetVideoProcessRenderTarget</i> returns one of the following values:

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
The render target surface is successfully set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>SetVideoProcessRenderTarget</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -remarks



<i>SetVideoProcessRenderTarget</i> can be called only outside of a <a href="https://msdn.microsoft.com/1b7b1774-3144-4929-83d8-c52a7de6936d">VideoProcessBeginFrame</a>/<a href="https://msdn.microsoft.com/a5be6834-bb27-4da0-8802-25a9ca58c101">VideoProcessEndFrame</a> block. 

All video processing render targets are created by setting the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544644">D3DDDI_RESOURCEFLAGS</a>.<b>VideoProcessRenderTarget</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a> structure in a call to the <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a> function. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543372">D3DDDIARG_SETVIDEOPROCESSRENDERTARGET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544644">D3DDDI_RESOURCEFLAGS</a>
 

 

