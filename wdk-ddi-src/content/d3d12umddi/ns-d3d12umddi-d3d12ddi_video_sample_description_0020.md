---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020
title: D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020
author: windows-driver-content
description: Describes the width, height, format, and color space of a picture buffer.
old-location: display\d3d12ddi_video_sample_description.htm
old-project: display
ms.assetid: B9918A06-6C10-4AD7-97EC-4FA0BC5319AD
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020 structure [Display Devices], D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020, d3d12umddi/D3D12DDI_VIDEO_SAMPLE_DESCRIPTION, display.d3d12ddi_video_sample_description
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
-	D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020
---

# D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020 structure


## -description


Describes the width, height, format, and color space of a picture buffer.


## -syntax


````
typedef struct D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020 {
  UINT                                   Width;
  UINT                                   Height;
  D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020 Format;
} D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020;
````


## -struct-fields




### -field Width

The width of the sample.


### -field Height

The height of the sample.


### -field Format

The format and color space of the sample.  For more information, see the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_format_description_0020.md">D3D12DDI_VIDEO_FORMAT_DESCRIPTION</a> structure.


## -see-also

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_format_description_0020.md">D3D12DDI_VIDEO_FORMAT_DESCRIPTION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

