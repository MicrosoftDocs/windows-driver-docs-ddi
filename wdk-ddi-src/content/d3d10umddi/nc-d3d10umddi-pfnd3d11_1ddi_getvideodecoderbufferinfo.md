---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEODECODERBUFFERINFO
title: PFND3D11_1DDI_GETVIDEODECODERBUFFERINFO
description: Queries the description of a video decoder buffer for a specified video operation.
old-location: display\getvideodecoderbufferinfo.htm
ms.assetid: f129ae04-da7f-4681-a266-ac13317a895d
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_GETVIDEODECODERBUFFERINFO, PFND3D11_1DDI_GETVIDEODECODERBUFFERINFO callback, d3d10umddi/pfnGetVideoDecoderBufferInfo, display.getvideodecoderbufferinfo, pfnGetVideoDecoderBufferInfo, pfnGetVideoDecoderBufferInfo callback function [Display Devices]
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
-	pfnGetVideoDecoderBufferInfo
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_GETVIDEODECODERBUFFERINFO callback function


## -description


Queries the description of a video decoder buffer for a specified video operation.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

*pDecodeDesc* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450951">D3D11_1DDI_VIDEO_DECODER_DESC</a> structure that specifies the video decoder operation.

### -param Arg2

*Index* [in]

The zero-based index of the video decoder buffer type that is used for the specified operation. The display miniport driver returns the maximum number of video decoder buffer types that are required for the operation through a call to its <a href="https://msdn.microsoft.com/library/windows/hardware/hh451663">GetVideoDecoderBufferTypeCount</a> function.


### -param *

*pInfo* [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450943">D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO</a> structure that describes the video decoder buffer.


## -returns



This callback function does not return a value.




## -remarks



The Microsoft Direct3D runtime verifies that the <i>pDecodeDesc</i>  and <i>Index</i> parameter data is valid before it calls the <b>GetVideoDecoderBufferInfo</b> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450943">D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450951">D3D11_1DDI_VIDEO_DECODER_DESC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451663">GetVideoDecoderBufferTypeCount</a>
 

 

