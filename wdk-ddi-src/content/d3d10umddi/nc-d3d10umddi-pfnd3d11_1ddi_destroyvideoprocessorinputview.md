---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW
title: PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW (d3d10umddi.h)
description: Releases resources for the video processor input view that were created through a call to the CreateVideoProcessorInputView function.
old-location: display\destroyvideoprocessorinputview.htm
ms.assetid: 3a815201-091b-4c85-a62a-2cdbbaf0bf95
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW, PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW callback, d3d10umddi/pfnDestroyVideoProcessorInputView, display.destroyvideoprocessorinputview, pfnDestroyVideoProcessorInputView, pfnDestroyVideoProcessorInputView callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d10umddi/pfnDestroyVideoProcessorInputView"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- pfnDestroyVideoProcessorInputView
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW callback function


## -description


Releases resources for the video processor input view that were created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorinputview">CreateVideoProcessorInputView</a> function.



## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hView* [in]

A handle to the driver's private data for the video processor input view. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorinputview">CreateVideoProcessorInputView</a>.


## -returns



This callback function does not return a value.



