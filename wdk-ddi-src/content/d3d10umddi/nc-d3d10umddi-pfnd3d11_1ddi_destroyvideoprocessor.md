---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYVIDEOPROCESSOR
title: PFND3D11_1DDI_DESTROYVIDEOPROCESSOR
author: windows-driver-content
description: Releases resources for the video processor object that were created through a call to the CreateVideoProcessor function.
old-location: display\destroyvideoprocessor1.htm
old-project: display
ms.assetid: a04776ba-bc80-498e-b25d-511ecb03fb63
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3D11_1DDI_DESTROYVIDEOPROCESSOR, PFND3D11_1DDI_DESTROYVIDEOPROCESSOR callback, d3d10umddi/pfnDestroyVideoProcessor, display.destroyvideoprocessor1, display.pfndestroyvideoprocessor1, pfnDestroyVideoProcessor, pfnDestroyVideoProcessor callback function [Display Devices]
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
-	pfnDestroyVideoProcessor
product: Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_DESTROYVIDEOPROCESSOR callback function


## -description


Releases resources for the video processor object that were created through a call to the <a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a> function.



## -parameters




### -param Arg1


### -param Arg2








#### - hDevice [in]

A handle to the display device (graphics context).




#### - hProcessor [in]

A handle to the driver's private data for the video processor object. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a>.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a>
 

 

