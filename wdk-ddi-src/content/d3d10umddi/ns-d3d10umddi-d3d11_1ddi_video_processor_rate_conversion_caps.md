---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS
author: windows-driver-content
description: Defines a group of video processor capabilities that are associated with frame-rate conversion, including deinterlacing and inverse telecine.
old-location: display\d3d11_1ddi_video_processor_rate_conversion_caps.htm
old-project: display
ms.assetid: 1b66f203-1c74-4b5e-82ae-7dfdc88da2b4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d11_1ddi_video_processor_rate_conversion_caps, D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS, D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS
---

# D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS structure


## -description


Defines a group of video processor capabilities that are associated with frame-rate conversion, including deinterlacing and inverse telecine.


## -syntax


````
typedef struct D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS {
  UINT PastFrames;
  UINT FutureFrames;
  UINT ConversionCaps;
  UINT ITelecineCaps;
  UINT CustomRateCount;
} D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS;
````


## -struct-fields




### -field PastFrames

The number of past reference frames required to perform the optimal video processing.


### -field FutureFrames

The number of future reference frames required to perform the optimal video processing.


### -field ConversionCaps

A bitwise <b>OR</b> of zero or more member values from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_conversion_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS</a> structure.


### -field ITelecineCaps

A bitwise <b>OR</b> of zero or more constant values from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_itelecine_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS</a> enumeration.


### -field CustomRateCount

The number of custom frame rates that the driver supports. To get the list of custom frame rates, call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcustomrate.md">GetVideoProcessorCustomRate</a> function.


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcustomrate.md">GetVideoProcessorCustomRate</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_rate_conversion_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_conversion_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_itelecine_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

