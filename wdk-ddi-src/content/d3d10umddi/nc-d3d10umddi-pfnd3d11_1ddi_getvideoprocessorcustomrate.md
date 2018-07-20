---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEOPROCESSORCUSTOMRATE
title: PFND3D11_1DDI_GETVIDEOPROCESSORCUSTOMRATE
author: windows-driver-content
description: Queries a custom frame rate that is associated with a rate conversion capability group.
old-location: display\getvideoprocessorcustomrate.htm
tech.root: display
ms.assetid: 49aec00a-8d63-4ec9-966a-0826354fbbe0
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D11_1DDI_GETVIDEOPROCESSORCUSTOMRATE, PFND3D11_1DDI_GETVIDEOPROCESSORCUSTOMRATE callback, d3d10umddi/pfnGetVideoProcessorCustomRate, display.getvideoprocessorcustomrate, pfnGetVideoProcessorCustomRate, pfnGetVideoProcessorCustomRate callback function [Display Devices]
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
-	pfnGetVideoProcessorCustomRate
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_GETVIDEOPROCESSORCUSTOMRATE callback function


## -description


Queries a custom frame rate that is associated with a rate conversion capability group. 


## -parameters




### -param Arg1


### -param Arg2


### -param Arg3


### -param Arg4


### -param *








#### - CustomRateIndex [in]

The zero-based index of the custom rate to query. For more information, see the Remarks section.


#### - RateConversionIndex [in]

The zero-based index of the frame-rate conversion capability group. For more information, see the Remarks section.


#### - hDevice [in]

A handle to the display device (graphics context).




#### - hProcessorEnum [in]

A handle to a video processor enumeration object that was created through a call to the <a href="https://msdn.microsoft.com/38c27502-7e8a-45a1-8a7c-315300502480">CreateVideoProcessorEnum</a> function.




#### - pRate [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450977">D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE</a> structure that contains the attributes of the specified custom rate.




## -returns



This callback function does not return a value.




## -remarks



The display miniport driver returns the maximum number of frame-rate conversion capabilities that it supports through the <b>RateConversionCapsCount</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450968">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure. The driver returns a pointer to this structure through its <a href="https://msdn.microsoft.com/library/windows/hardware/hh451674">GetVideoProcessorCaps</a> function. In addition, the attributes of a frame-rate conversion capability group can be queried by calling the <b>GetVideoProcessorCaps</b> function.

The display miniport driver returns the maximum number of custom rates that it supports through the <b>CustomRateCount</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450990">D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS</a> structure. The driver returns a pointer to this structure through its <a href="https://msdn.microsoft.com/library/windows/hardware/hh451674">GetVideoProcessorCaps</a> function. In addition, the attributes of a frame-rate conversion capability group can be queried by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451690">GetVideoProcessorRateConversionCaps</a> function.




## -see-also




<a href="https://msdn.microsoft.com/38c27502-7e8a-45a1-8a7c-315300502480">CreateVideoProcessorEnum</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450968">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451674">GetVideoProcessorCaps</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451690">GetVideoProcessorRateConversionCaps</a>
 

 

