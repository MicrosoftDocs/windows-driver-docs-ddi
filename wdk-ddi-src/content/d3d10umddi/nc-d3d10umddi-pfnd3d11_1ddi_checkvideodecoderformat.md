---
UID: NC:d3d10umddi.PFND3D11_1DDI_CHECKVIDEODECODERFORMAT
title: PFND3D11_1DDI_CHECKVIDEODECODERFORMAT
author: windows-driver-content
description: Determines whether a specified format can be used as a video decoder output format for a specified DirectX Video Acceleration (DXVA) profile.
old-location: display\checkvideodecoderformat.htm
ms.assetid: 6bde6e00-70ba-4fa5-9cc0-9884ce7381ed
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: CheckVideoDecoderFormat, CheckVideoDecoderFormat callback function [Display Devices], PFND3D11_1DDI_CHECKVIDEODECODERFORMAT, PFND3D11_1DDI_CHECKVIDEODECODERFORMAT callback, d3d10umddi/CheckVideoDecoderFormat, display.checkvideodecoderformat
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
-	CheckVideoDecoderFormat
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_CHECKVIDEODECODERFORMAT callback function


## -description


Determines whether a specified format can be used as a video decoder output format for a specified DirectX Video Acceleration (DXVA) profile.


## -parameters




### -param Arg1


### -param *








### -param Arg2


#### - Format [in]

A DXGI_FORMAT value that specifies the output format. Typical values include DXGI_FORMAT_NV12 and DXGI_FORMAT_420_OPAQUE.


#### - hDevice [in]

A handle to the display device (graphics context).




#### - pBool [out]

A BOOL value that, if TRUE, specifies that the specified format can be used  for the specified DXVA profile.


#### - pDecoderProfile [in]

A pointer to a GUID that identifies the DXVA profile. 


## -returns



This callback function does not return a value.




## -remarks



This function is not expected to fail.



