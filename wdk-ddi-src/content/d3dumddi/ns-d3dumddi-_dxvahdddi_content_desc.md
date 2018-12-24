---
UID: NS:d3dumddi._DXVAHDDDI_CONTENT_DESC
title: "_DXVAHDDDI_CONTENT_DESC"
description: The DXVAHDDDI_CONTENT_DESC structure describes the video content that a decode device processes.
old-location: display\dxvahdddi_content_desc.htm
tech.root: display
ms.assetid: 635a4a47-11b8-4d78-871e-21ee438880df
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_8b90044d-bce5-49b0-b6ff-be34ab09a62e.xml, DXVAHDDDI_CONTENT_DESC, DXVAHDDDI_CONTENT_DESC structure [Display Devices], _DXVAHDDDI_CONTENT_DESC, d3dumddi/DXVAHDDDI_CONTENT_DESC, display.dxvahdddi_content_desc
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	DXVAHDDDI_CONTENT_DESC
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_CONTENT_DESC
---

# _DXVAHDDDI_CONTENT_DESC structure


## -description


The DXVAHDDDI_CONTENT_DESC structure describes the video content that a decode device processes. 


## -struct-fields




### -field InputFrameFormat

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563056">DXVAHDDDI_FRAME_FORMAT</a>-typed value that indicates the frame format of the input video stream. 


### -field InputFrameRate


      [in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563064">DXVAHDDDI_RATIONAL</a> structure that specifies a fractional value that represents the frame rate of the input video stream. 
     


### -field InputWidth

[in] The width, in pixels, of the input video stream. 


### -field InputHeight

[in] The height, in pixels, of the input video stream. 


### -field OutputFrameRate


      [in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563064">DXVAHDDDI_RATIONAL</a> structure that specifies a fractional value that represents the frame rate of the output. 
     


### -field OutputWidth

[in] The width, in pixels, of the output video stream. 


### -field OutputHeight

[in] The height, in pixels, of the output video stream. 


## -remarks



The driver can use the information in the members of DXVAHDDDI_CONTENT_DESC to optimize its capabilities. For example, the driver might not require to expose costly capabilities for high-definition content and the de-interlacing capability for progressive content. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563056">DXVAHDDDI_FRAME_FORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563064">DXVAHDDDI_RATIONAL</a>
 

 

