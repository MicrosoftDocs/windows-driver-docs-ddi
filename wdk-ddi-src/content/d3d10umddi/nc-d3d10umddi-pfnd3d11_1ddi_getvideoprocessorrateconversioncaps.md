---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEOPROCESSORRATECONVERSIONCAPS
title: PFND3D11_1DDI_GETVIDEOPROCESSORRATECONVERSIONCAPS
author: windows-driver-content
description: Queries a specified group of video processing capabilities that are associated with frame-rate conversion, including deinterlacing and inverse telecine.
old-location: display\getvideoprocessorrateconversioncaps.htm
tech.root: display
ms.assetid: c77b722f-e023-4e3e-9dff-616d0ab0a6a2
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D11_1DDI_GETVIDEOPROCESSORRATECONVERSIONCAPS, PFND3D11_1DDI_GETVIDEOPROCESSORRATECONVERSIONCAPS callback, d3d10umddi/pfnGetVideoProcessorRateConversionCaps, display.getvideoprocessorrateconversioncaps, pfnGetVideoProcessorRateConversionCaps, pfnGetVideoProcessorRateConversionCaps callback function [Display Devices]
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
-	pfnGetVideoProcessorRateConversionCaps
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_GETVIDEOPROCESSORRATECONVERSIONCAPS callback function


## -description


Queries a specified group of video processing capabilities that are associated with frame-rate conversion, including deinterlacing and inverse telecine.



## -parameters




### -param Arg1


### -param Arg2


### -param Arg3


### -param *








#### - RateConversionIndex [in]

The zero-based index of the frame-rate conversion capability group. For more information, see the Remarks section.


#### - hDevice [in]

A handle to the display device (graphics context).




#### - hProcessorEnum [in]

A handle to a video processor enumeration object that was created through a call to the <a href="https://msdn.microsoft.com/38c27502-7e8a-45a1-8a7c-315300502480">CreateVideoProcessorEnum</a> function.




#### - pCaps [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450990">D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS</a> structure that contains the attributes of  the specified rate conversion capability group.


## -returns



This callback function does not return a value.




## -remarks



The display miniport driver returns the maximum number of frame-rate conversion capabilities that it supports through the <b>RateConversionCapsCount</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450968">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure. The driver returns a pointer to this structure through its <a href="https://msdn.microsoft.com/library/windows/hardware/hh451674">GetVideoProcessorCaps</a> function.




## -see-also




<a href="https://msdn.microsoft.com/38c27502-7e8a-45a1-8a7c-315300502480">CreateVideoProcessorEnum</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450968">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451674">GetVideoProcessorCaps</a>
 

 

