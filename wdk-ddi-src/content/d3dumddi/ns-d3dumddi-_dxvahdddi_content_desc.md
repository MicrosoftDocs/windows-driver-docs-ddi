---
UID: NS:d3dumddi._DXVAHDDDI_CONTENT_DESC
title: "_DXVAHDDDI_CONTENT_DESC"
author: windows-driver-content
description: The DXVAHDDDI_CONTENT_DESC structure describes the video content that a decode device processes.
old-location: display\dxvahdddi_content_desc.htm
old-project: display
ms.assetid: 635a4a47-11b8-4d78-871e-21ee438880df
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVAHDDDI_CONTENT_DESC, DXVAHDDDI_CONTENT_DESC structure [Display Devices], display.dxvahdddi_content_desc, _DXVAHDDDI_CONTENT_DESC, DXVA2_Structs_8b90044d-bce5-49b0-b6ff-be34ab09a62e.xml, d3dumddi/DXVAHDDDI_CONTENT_DESC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_CONTENT_DESC is supported beginning with the Windows 7 operating system.
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
-	d3dumddi.h
apiname:
-	DXVAHDDDI_CONTENT_DESC
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_CONTENT_DESC
---

# _DXVAHDDDI_CONTENT_DESC structure


## -description


The DXVAHDDDI_CONTENT_DESC structure describes the video content that a decode device processes. 


## -syntax


````
typedef struct _DXVAHDDDI_CONTENT_DESC {
  DXVAHDDDI_FRAME_FORMAT InputFrameFormat;
  DXVAHDDDI_RATIONAL     InputFrameRate;
  UINT                   InputWidth;
  UINT                   InputHeight;
  DXVAHDDDI_RATIONAL     OutputFrameRate;
  UINT                   OutputWidth;
  UINT                   OutputHeight;
} DXVAHDDDI_CONTENT_DESC;
````


## -struct-fields




### -field InputFrameFormat

[in] A <a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_frame_format.md">DXVAHDDDI_FRAME_FORMAT</a>-typed value that indicates the frame format of the input video stream. 


### -field InputFrameRate


      [in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_rational.md">DXVAHDDDI_RATIONAL</a> structure that specifies a fractional value that represents the frame rate of the input video stream. 
     


### -field InputWidth

[in] The width, in pixels, of the input video stream. 


### -field InputHeight

[in] The height, in pixels, of the input video stream. 


### -field OutputFrameRate


      [in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_rational.md">DXVAHDDDI_RATIONAL</a> structure that specifies a fractional value that represents the frame rate of the output. 
     


### -field OutputWidth

[in] The width, in pixels, of the output video stream. 


### -field OutputHeight

[in] The height, in pixels, of the output video stream. 


## -remarks


The driver can use the information in the members of DXVAHDDDI_CONTENT_DESC to optimize its capabilities. For example, the driver might not require to expose costly capabilities for high-definition content and the de-interlacing capability for progressive content. 



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_rational.md">DXVAHDDDI_RATIONAL</a>

<a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_frame_format.md">DXVAHDDDI_FRAME_FORMAT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_CONTENT_DESC structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

