---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020
title: D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020
author: windows-driver-content
description: Defines the combination of a pixel format and color space for a resource content description.
old-location: display\d3d12ddi_video_format_description.htm
old-project: display
ms.assetid: 47C0C369-B31B-4291-A420-A1E75BA990CF
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d12ddi_video_format_description, D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020, D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020
---

# D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020 structure


## -description


Defines the combination of a pixel format and color space for a resource content description.


## -syntax


````
typedef struct D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020 {
  DXGI_FORMAT           Format;
  DXGI_COLOR_SPACE_TYPE ColorSpace;
} D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020;
````


## -struct-fields




### -field Format

The format of the data.  For more information, see the  <a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a> enumeration.


### -field ColorSpace

The color space of the data.  For more information, see the <a href="https://msdn.microsoft.com/E25C933F-0DB3-4BC4-9755-9361B2B9B9CB">DXGI_COLOR_SPACE_TYPE</a> enumeration.


## -remarks



Conversions exposed through the decoder must have a hardware advantage compared to a conversion that could be accomplished through the app via a decode and a video process BLT.  This typically means the video hardware write the unconverted reference frame and the converted output (both outputs) without a separate step that reads the unconverted reference frame to produce the converted output.


The one exception is that all drivers are required to support a conversion to remove the D3D12DDI_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY flag where the source and destination format, colorspace, and size are equal.  Hardware may not actually require the D3D12DDI_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY flag, but if it is used, driver may implement this conversion with a copy operation.  





## -see-also

<a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a>



<a href="https://msdn.microsoft.com/E25C933F-0DB3-4BC4-9755-9361B2B9B9CB">DXGI_COLOR_SPACE_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

