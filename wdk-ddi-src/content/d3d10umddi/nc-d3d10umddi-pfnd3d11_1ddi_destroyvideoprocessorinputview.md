---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW
title: PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW
author: windows-driver-content
description: Releases resources for the video processor input view that were created through a call to the CreateVideoProcessorInputView function.
old-location: display\destroyvideoprocessorinputview.htm
old-project: display
ms.assetid: 3a815201-091b-4c85-a62a-2cdbbaf0bf95
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.destroyvideoprocessorinputview, pfnDestroyVideoProcessorInputView callback function [Display Devices], pfnDestroyVideoProcessorInputView, PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW, PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW, d3d10umddi/pfnDestroyVideoProcessorInputView
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
-	pfnDestroyVideoProcessorInputView
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW callback


## -description


Releases resources for the video processor input view that were created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorinputview.md">CreateVideoProcessorInputView</a> function.



## -prototype


````
PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW pfnDestroyVideoProcessorInputView;

VOID APIENTRY* pfnDestroyVideoProcessorInputView(
  _In_ D3D10DDI_HDEVICE                    hDevice,
  _In_ D3D11_1DDI_HVIDEOPROCESSORINPUTVIEW hView
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D11_1DDI_HVIDEOPROCESSORINPUTVIEW








#### - hDevice [in]

A handle to the display device (graphics context).




#### - hView [in]

A handle to the driver's private data for the video processor input view. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorinputview.md">CreateVideoProcessorInputView</a>.


## -returns



This callback function does not return a value.



