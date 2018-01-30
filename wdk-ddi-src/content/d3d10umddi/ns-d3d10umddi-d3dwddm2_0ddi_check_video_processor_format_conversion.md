---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION
title: D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION
author: windows-driver-content
description: D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION is used with CheckVideoProcessorFormatConversion to indicate whether the driver supports a specific format/color space conversion combination.
old-location: display\d3dwddm2_0ddi_check_video_processor_format_conversion.htm
old-project: display
ms.assetid: 3259CEB7-E902-4040-B99E-D0609935E804
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION, D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION, D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION structure [Display Devices], display.d3dwddm2_0ddi_check_video_processor_format_conversion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION
---

# D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION structure


## -description


<b>D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION</b> is used with <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_checkvideoprocessorformatconversion.md">CheckVideoProcessorFormatConversion</a> to indicate whether the driver supports a specific format/color space conversion combination.


## -syntax


````
typedef struct D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION {
  DXGI_FORMAT             InputFormat;
  D3DDDI_COLOR_SPACE_TYPE InputColorSpace;
  DXGI_FORMAT             OutputFormat;
  D3DDDI_COLOR_SPACE_TYPE OutputColorSpace;
  BOOL                    Supported;
} D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION;
````


## -struct-fields




### -field InputFormat

Indicates the format of the video processor input.


### -field InputColorSpace

Indicates the colorspace of the video processor input.


### -field OutputFormat

Indicates the format of the video processor output.


### -field OutputColorSpace

Indicates the colorspace of the video processor output.


### -field Supported

The driver sets this to <b>TRUE</b> if the conversion between the input format/color space and the output format/color space is supported.


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_checkvideoprocessorformatconversion.md">CheckVideoProcessorFormatConversion</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

