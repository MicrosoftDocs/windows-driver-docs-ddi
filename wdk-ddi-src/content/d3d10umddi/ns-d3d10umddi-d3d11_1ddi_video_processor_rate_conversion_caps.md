---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS
author: windows-driver-content
description: Defines a group of video processor capabilities that are associated with frame-rate conversion, including deinterlacing and inverse telecine.
old-location: display\d3d11_1ddi_video_processor_rate_conversion_caps.htm
old-project: display
ms.assetid: 1b66f203-1c74-4b5e-82ae-7dfdc88da2b4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS, D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS, display.d3d11_1ddi_video_processor_rate_conversion_caps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS
product:
- Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS
---

# D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS structure


## -description


Defines a group of video processor capabilities that are associated with frame-rate conversion, including deinterlacing and inverse telecine.


## -struct-fields




### -field PastFrames

The number of past reference frames required to perform the optimal video processing.


### -field FutureFrames

The number of future reference frames required to perform the optimal video processing.


### -field ConversionCaps

A bitwise <b>OR</b> of zero or more member values from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450975">D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS</a> structure.


### -field ITelecineCaps

A bitwise <b>OR</b> of zero or more constant values from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450988">D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS</a> enumeration.


### -field CustomRateCount

The number of custom frame rates that the driver supports. To get the list of custom frame rates, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451676">GetVideoProcessorCustomRate</a> function.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450975">D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450988">D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450990">D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451676">GetVideoProcessorCustomRate</a>
 

 

