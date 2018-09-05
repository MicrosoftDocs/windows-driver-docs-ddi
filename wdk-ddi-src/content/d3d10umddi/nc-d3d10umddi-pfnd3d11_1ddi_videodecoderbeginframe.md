---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEODECODERBEGINFRAME
title: PFND3D11_1DDI_VIDEODECODERBEGINFRAME
author: windows-driver-content
description: Starts a DirectX Video Acceleration (DXVA) decoding operation to decode a video frame.
old-location: display\videodecoderbeginframe.htm
ms.assetid: 5aebc8c9-baa1-457f-9e46-3a86929ba0b5
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D11_1DDI_VIDEODECODERBEGINFRAME, PFND3D11_1DDI_VIDEODECODERBEGINFRAME callback, d3d10umddi/pfnVideoDecoderBeginFrame, display.videodecoderbeginframe, pfnVideoDecoderBeginFrame, pfnVideoDecoderBeginFrame callback function [Display Devices]
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
-	pfnVideoDecoderBeginFrame
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEODECODERBEGINFRAME callback function


## -description


Starts a DirectX Video Acceleration (DXVA) decoding operation to decode a video frame.




## -parameters




### -param Arg1


### -param Arg2


### -param *








#### - hDecoder [in]

A handle to the video decoder object that was created through a call to the <a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a> function.




#### - hDevice [in]

A handle to the display device (graphics context).




#### - pBeginFrame [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406328">D3D11_1DDIARG_VIDEODECODERBEGINFRAME</a> structure. For more information, see the Remarks section.


## -returns



<b>VideoDecoderBeginFrame</b> returns one of the following values:

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
The decoding operation was started successfully.

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



If the <b>VideoDecoderBeginFrame</b> returns <b>S_OK</b>, the Microsoft Direct3D runtime calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451701">VideoDecoderSubmitBuffers</a> function  to perform the decoding operations. When all decoding operations have been executed, the runtime calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451698">VideoDecoderEndFrame</a> function to stop the decoding operation on a video frame.



<div class="alert"><b>Note</b>  Each call to <b>VideoDecoderBeginFrame</b> must have a matching call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh451698">VideoDecoderEndFrame</a>, and <b>VideoDecoderBeginFrame</b> calls cannot be nested.</div>
<div> </div>
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh406328">D3D11_1DDIARG_VIDEODECODERBEGINFRAME</a> structure contains the following data:

<ul>
<li>
The resource that will receive the decrypted and decoded data.

</li>
<li>
A content key that was used to encrypt the video frame data. 

If the <b>pContentKey</b> member of this structure is not set to NULL, the buffer that is referenced by this member contains a per-frame content key. This key must be used to decrypt the data instead of using the session key.

<div class="alert"><b>Note</b>  If the <b>pContentKey</b> member is not set to NULL, the buffer that is referenced by this member is encrypted by using the session key with the AES-ECB algorithm.</div>
<div> </div>
If the <b>pContentKey</b> member is set to NULL, the video frame data should be decrypted by using the session key.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451698">VideoDecoderEndFrame</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451701">VideoDecoderSubmitBuffers</a>
 

 

