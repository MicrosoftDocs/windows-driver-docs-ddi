---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYVIDEODECODER
title: PFND3D11_1DDI_DESTROYVIDEODECODER
author: windows-driver-content
description: Releases resources for the video decoder object that were created through a call to the CreateVideoDecoder function.
old-location: display\destroyvideodecoder.htm
old-project: display
ms.assetid: 541f4c9b-3193-46a8-9979-74456168988e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D11_1DDI_DESTROYVIDEODECODER, d3d10umddi/pfnDestroyVideoDecoder, display.destroyvideodecoder, pfnDestroyVideoDecoder, pfnDestroyVideoDecoder callback function [Display Devices]
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
-	pfnDestroyVideoDecoder
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_DESTROYVIDEODECODER callback


## -description


Releases resources for the video decoder object that were created through a call to the <a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a> function.



## -parameters




### -param Arg1


### -param Arg2








#### - hDecoder [in]

A handle to the driver's private data for the video decoder object. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a>.


#### - hDevice [in]

A handle to the display device (graphics context).




## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a>
 

 

