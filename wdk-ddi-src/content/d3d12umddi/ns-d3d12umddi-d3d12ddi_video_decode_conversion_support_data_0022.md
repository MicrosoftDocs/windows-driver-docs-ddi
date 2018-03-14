---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022
title: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022
author: windows-driver-content
description: Specifies information used to check whether a color space conversion, format conversion, and scale are supported and whether it is required for real-time reasons or reference buffer format.
old-location: display\d3d12ddi_video_decode_conversion_support_data.htm
old-project: display
ms.assetid: E9FA4CEB-84D3-42A6-B36A-B411922F19AE
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022, D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022, display.d3d12ddi_video_decode_conversion_support_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
-	D3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022
---

# D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022 structure


## -description


Specifies information used to check whether a color space conversion, format conversion, and scale are supported and whether it is required for real-time reasons or reference buffer format.  


## -syntax


````
typedef struct D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022 {
  UINT                                                NodeIndex;
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020            Configuration;
  D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020              DecodeSample;
  D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020              OutputFormat;
  DXGI_RATIONAL                                       FrameRate;
  UINT                                                BitRate;
  D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS_0020 SupportFlags;
  D3D12DDI_VIDEO_SCALE_SUPPORT_0022                   ScaleSupport;
} D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022;
````


## -struct-fields




### -field NodeIndex

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.


### -field Configuration

The decode profile and bitstream encryption.  For more information, see the  <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020.md">D3D12DDI_VIDEO_DECODE_CONFIGURATION</a> enumeration.


### -field DecodeSample

The source decoded as sample description.  For more information, see the  <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_sample_description_0020.md">D3D12DDI_VIDEO_SAMPLE_DESCRIPTION</a> structure.


### -field OutputFormat

The output sample description.  For more information, see the  <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_format_description_0020.md">D3D12DDI_VIDEO_FORMAT_DESCRIPTION</a> structure.


### -field FrameRate

The frame rate of the video content. This is used by the driver to determine whether the video can be decoded in real time.


### -field BitRate

The average bits per second data compression rate for the compressed video stream.  This is used by the driver to determine whether the video can be decoded in real time.


### -field SupportFlags

The returned supported flags. For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_conversion_support_flags_0020.md">D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS</a> enumeration.


### -field ScaleSupport

The returned supported output size range for decode conversion.  For more information, see the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_scale_support_0022.md">D3D12DDI_VIDEO_SCALE_SUPPORT</a> structure.


## -remarks



The check is made through <a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md">pfnGetCaps</a> with the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddicaps_type.md">D3D12DDICAPS_TYPE</a> set to a value of <b>D3D12DDICAPS_TYPE_VIDEO_DECODE_CONVERSION_SUPPORT</b>.

If the color space and format conversion is reported, the <i>SupportedFlags</i> has the <b>D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS_SUPPORTED</b> flag set.  

Callers should check the <i>ScaleSupport</i> parameter to understand if the scale is supported.




## -see-also

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddicaps_type.md">D3D12DDICAPS_TYPE</a>



<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_sample_description_0020.md">D3D12DDI_VIDEO_SAMPLE_DESCRIPTION</a>



<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_conversion_support_flags_0020.md">D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS</a>



<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_scale_support_0022.md">D3D12DDI_VIDEO_SCALE_SUPPORT</a>



<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_format_description_0020.md">D3D12DDI_VIDEO_FORMAT_DESCRIPTION</a>



<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020.md">D3D12DDI_VIDEO_DECODE_CONFIGURATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022 structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

