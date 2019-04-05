---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYVIDEOPROCESSORENUM
title: PFND3D11_1DDI_DESTROYVIDEOPROCESSORENUM (d3d10umddi.h)
description: Releases resources for the video processor enumeration object that were created through a call to the CreateVideoProcessorEnum function.
old-location: display\destroyvideoprocessorenum.htm
ms.assetid: a4325993-aa87-466e-8e89-40bede1e0306
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_DESTROYVIDEOPROCESSORENUM, PFND3D11_1DDI_DESTROYVIDEOPROCESSORENUM callback, d3d10umddi/pfnDestroyVideoProcessorEnum, display.destroyvideoprocessorenum, pfnDestroyVideoProcessorEnum, pfnDestroyVideoProcessorEnum callback function [Display Devices]
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- pfnDestroyVideoProcessorEnum
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_DESTROYVIDEOPROCESSORENUM callback function


## -description


Releases resources for the video processor enumeration object that were created through a call to the <a href="https://msdn.microsoft.com/38c27502-7e8a-45a1-8a7c-315300502480">CreateVideoProcessorEnum</a> function.



## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hProcessorEnum* [in]

A handle to the driver's private data for the video processor enumeration object. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="https://msdn.microsoft.com/38c27502-7e8a-45a1-8a7c-315300502480">CreateVideoProcessorEnum</a>.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/38c27502-7e8a-45a1-8a7c-315300502480">CreateVideoProcessorEnum</a>
 

 

