---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_CAPS
author: windows-driver-content
description: Describes the capabilities of a Microsoft Direct3D 11 video processor.
old-location: display\d3d11_1ddi_video_processor_caps.htm
old-project: display
ms.assetid: d825a0d1-fa58-4525-bf90-eb7eaee0cfba
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 1, 3, A, C, D, D3D11_1DDI_VIDEO_PROCESSOR_CAPS, D3D11_1DDI_VIDEO_PROCESSOR_CAPS structure [Display Devices], E, I, O, P, R, S, V, _, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_CAPS, display.d3d11_1ddi_video_processor_caps"
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
-	D3D11_1DDI_VIDEO_PROCESSOR_CAPS
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_CAPS
---

# D3D11_1DDI_VIDEO_PROCESSOR_CAPS structure


## -description


Describes the capabilities of a Microsoft Direct3D 11 video processor.


## -syntax


````
typedef struct D3D11_1DDI_VIDEO_PROCESSOR_CAPS {
  UINT DeviceCaps;
  UINT FeatureCaps;
  UINT FilterCaps;
  UINT InputFormatCaps;
  UINT AutoStreamCaps;
  UINT StereoCaps;
  UINT RateConversionCapsCount;
  UINT MaxInputStreams;
  UINT MaxStreamStates;
} D3D11_1DDI_VIDEO_PROCESSOR_CAPS;
````


## -struct-fields




### -field DeviceCaps

A bitwise <b>OR</b> of zero or more flags from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_device_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS</a> enumeration.


### -field FeatureCaps

A bitwise <b>OR</b> of zero or more flags from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_feature_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS</a> enumeration.


### -field FilterCaps

A bitwise <b>OR</b> of zero or more flags from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_filter_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS</a> enumeration.


### -field InputFormatCaps

A bitwise <b>OR</b> of zero or more flags from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_format_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS</a> enumeration.


### -field AutoStreamCaps

A bitwise <b>OR</b> of zero or more flags from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_auto_stream_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_AUTO_STREAM_CAPS</a> enumeration.


### -field StereoCaps

A bitwise <b>OR</b> of zero or more flags from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS</a> enumeration.


### -field RateConversionCapsCount

The number of frame-rate conversion capabilities. To enumerate the frame-rate conversion capabilities, call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorrateconversioncaps.md">GetVideoProcessorRateConversionCaps</a> function.


### -field MaxInputStreams

The maximum number of input streams that can be enabled at the same time.


### -field MaxStreamStates

The maximum number of input streams for which the device can store state data.


## -remarks



The video processor stores state information for each input stream. These states persist between blits. With each blit, the application selects which streams to enable or disable. Disabling a stream does not affect the state information for that stream.

The <b>MaxStreamStates</b> member gives the maximum number of stream states that can be saved. The <b>MaxInputStreams</b> member gives the maximum number of streams that can be enabled during a blit. These two values can differ.




## -see-also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_format_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_filter_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorrateconversioncaps.md">GetVideoProcessorRateConversionCaps</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_feature_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_auto_stream_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_AUTO_STREAM_CAPS</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_device_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_VIDEO_PROCESSOR_CAPS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

