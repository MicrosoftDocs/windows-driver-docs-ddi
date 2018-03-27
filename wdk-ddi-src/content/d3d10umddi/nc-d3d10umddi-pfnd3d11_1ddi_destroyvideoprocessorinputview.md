---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW
title: PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW
author: windows-driver-content
description: Releases resources for the video processor input view that were created through a call to the CreateVideoProcessorInputView function.
old-location: display\destroyvideoprocessorinputview.htm
old-project: display
ms.assetid: 3a815201-091b-4c85-a62a-2cdbbaf0bf95
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW, d3d10umddi/pfnDestroyVideoProcessorInputView, display.destroyvideoprocessorinputview, pfnDestroyVideoProcessorInputView, pfnDestroyVideoProcessorInputView callback function [Display Devices]
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
-	pfnDestroyVideoProcessorInputView
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW callback


## -description


Releases resources for the video processor input view that were created through a call to the <a href="https://msdn.microsoft.com/f3942c53-e366-41c5-9f43-d093fa6b6ed6">CreateVideoProcessorInputView</a> function.



## -parameters




### -param Arg1


### -param Arg2








#### - hDevice [in]

A handle to the display device (graphics context).




#### - hView [in]

A handle to the driver's private data for the video processor input view. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="https://msdn.microsoft.com/f3942c53-e366-41c5-9f43-d093fa6b6ed6">CreateVideoProcessorInputView</a>.


## -returns



This callback function does not return a value.



