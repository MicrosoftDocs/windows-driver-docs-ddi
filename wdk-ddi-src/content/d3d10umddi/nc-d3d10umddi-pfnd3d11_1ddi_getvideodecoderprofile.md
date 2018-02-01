---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEODECODERPROFILE
title: PFND3D11_1DDI_GETVIDEODECODERPROFILE
author: windows-driver-content
description: Queries the attributes of a specified video decoder profile.
old-location: display\getvideodecoderprofile.htm
old-project: display
ms.assetid: 75576152-0afd-4602-b481-bf1d6d9348b3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.getvideodecoderprofile, pfnGetVideoDecoderProfile callback function [Display Devices], pfnGetVideoDecoderProfile, PFND3D11_1DDI_GETVIDEODECODERPROFILE, PFND3D11_1DDI_GETVIDEODECODERPROFILE, d3d10umddi/pfnGetVideoDecoderProfile
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
-	pfnGetVideoDecoderProfile
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D11_1DDI_GETVIDEODECODERPROFILE callback


## -description


Queries the attributes of a specified video decoder profile.


## -prototype


````
PFND3D11_1DDI_GETVIDEODECODERPROFILE pfnGetVideoDecoderProfile;

VOID APIENTRY* pfnGetVideoDecoderProfile(
  _In_        D3D10DDI_HDEVICE              hDevice,
  _In_        UINT                          Index,
  _Out_ const D3D11_1DDI_VIDEO_DECODER_DESC *pDecodeDesc
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param UINT



### -param *






#### - Index [in]

The zero-based index of the video decoder profile. The display miniport driver returns the maximum number of video decoder profiles that it supports through a call to its <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderprofilecount.md">GetVideoDecoderProfileCount</a> function.


#### - hDevice [in]

A handle to the display device (graphics context).




#### - pDecodeDesc [out]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_desc.md">D3D11_1DDI_VIDEO_DECODER_DESC</a> structure that specifies the attributes of the specified video decoder profile.


## -returns


This callback function does not return a value.



## -remarks


The Microsoft Direct3D runtime verifies that the <i>Index</i> parameter data is valid before it calls the <b>GetVideoDecoderProfile</b> function.



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_desc.md">D3D11_1DDI_VIDEO_DECODER_DESC</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderprofilecount.md">GetVideoDecoderProfileCount</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_GETVIDEODECODERPROFILE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

