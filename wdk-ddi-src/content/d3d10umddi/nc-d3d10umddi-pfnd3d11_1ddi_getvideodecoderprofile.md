---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEODECODERPROFILE
title: PFND3D11_1DDI_GETVIDEODECODERPROFILE
author: windows-driver-content
description: Queries the attributes of a specified video decoder profile.
old-location: display\getvideodecoderprofile.htm
old-project: display
ms.assetid: 75576152-0afd-4602-b481-bf1d6d9348b3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D11_1DDI_GETVIDEODECODERPROFILE, d3d10umddi/pfnGetVideoDecoderProfile, display.getvideodecoderprofile, pfnGetVideoDecoderProfile, pfnGetVideoDecoderProfile callback function [Display Devices]
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
-	pfnGetVideoDecoderProfile
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_GETVIDEODECODERPROFILE callback


## -description


Queries the attributes of a specified video decoder profile.


## -parameters




### -param Arg1


### -param Arg2


### -param *








#### - Index [in]

The zero-based index of the video decoder profile. The display miniport driver returns the maximum number of video decoder profiles that it supports through a call to its <a href="https://msdn.microsoft.com/library/windows/hardware/hh451672">GetVideoDecoderProfileCount</a> function.


#### - hDevice [in]

A handle to the display device (graphics context).




#### - pDecodeDesc [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450951">D3D11_1DDI_VIDEO_DECODER_DESC</a> structure that specifies the attributes of the specified video decoder profile.


## -returns



This callback function does not return a value.




## -remarks



The Microsoft Direct3D runtime verifies that the <i>Index</i> parameter data is valid before it calls the <b>GetVideoDecoderProfile</b> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450951">D3D11_1DDI_VIDEO_DECODER_DESC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451672">GetVideoDecoderProfileCount</a>
 

 

