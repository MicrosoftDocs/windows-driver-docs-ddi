---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1
title: PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1
author: windows-driver-content
description: VideoDecoderSubmitBuffers1 submits one or more buffers for decoding.
old-location: display\videodecodersubmitbuffers1.htm
ms.assetid: 708A7F64-F8A8-4D0B-A824-CC8DD158216A
ms.date: 05/10/2018
ms.keywords: PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1, PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1 callback, d3d10umddi/pfnVideoDecoderSubmitBuffers1, display.videodecodersubmitbuffers1, pfnVideoDecoderSubmitBuffers1, pfnVideoDecoderSubmitBuffers1 callback function [Display Devices]
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	pfnVideoDecoderSubmitBuffers1
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1 callback function


## -description


<b>VideoDecoderSubmitBuffers1</b> submits one or more buffers for decoding.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hDecode [in]

A handle to the video decoder object that was created through a call to the <a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a>DDI. 


### -param BufferCount [in]

The number of buffers in the array that is referenced by the <b>pBufferDesc</b> member.


### -param *pBufferDesc [in]

A pointer to an array of one or more <a href="https://msdn.microsoft.com/library/windows/hardware/dn894619">D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1</a> structures. 


## -returns




      Returns one of the following values:

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
Private driver data was successfully returned.

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



The <b>pBufferDesc</b> member points to an array of one or more <a href="https://msdn.microsoft.com/library/windows/hardware/dn894619">D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1</a> structures. Each element in the array describes a compressed video frame buffer that is submitted for decoding. 




## -see-also




<a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn894619">D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1</a>
 

 

