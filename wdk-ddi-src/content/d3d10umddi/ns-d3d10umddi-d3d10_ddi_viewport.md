---
UID: NS:d3d10umddi.D3D10_DDI_VIEWPORT
title: D3D10_DDI_VIEWPORT
author: windows-driver-content
description: The D3D10_DDI_VIEWPORT structure describes a viewport.
old-location: display\d3d10_ddi_viewport.htm
old-project: display
ms.assetid: 5b2025ce-e0dd-434d-b92b-16ecaf24808f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d10_ddi_viewport, D3D10_DDI_VIEWPORT structure [Display Devices], d3d10umddi/D3D10_DDI_VIEWPORT, D3D10_DDI_VIEWPORT, UMDisplayDriver_Dx10param_Structs_820ac08a-01a2-4e47-8573-aedf3c3769e1.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3d10umddi.h
apiname:
-	D3D10_DDI_VIEWPORT
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_VIEWPORT
---

# D3D10_DDI_VIEWPORT structure


## -description


The D3D10_DDI_VIEWPORT structure describes a viewport.


## -syntax


````
typedef struct D3D10_DDI_VIEWPORT {
  FLOAT TopLeftX;
  FLOAT TopLeftY;
  FLOAT Width;
  FLOAT Height;
  FLOAT MinDepth;
  FLOAT MaxDepth;
} D3D10_DDI_VIEWPORT;
````


## -struct-fields




### -field TopLeftX

[in] A single-precision float vector for the top-left x-coordinate of the viewport.


### -field TopLeftY

[in] A single-precision float vector for the top-left y-coordinate of the viewport.


### -field Width


      [in] A single-precision float vector for the width of the viewport.
     


### -field Height

[in] A single-precision float vector for the height of the viewport.


### -field MinDepth

[in] A single-precision float vector for the minimum depth of the viewport.


### -field MaxDepth

[in] A single-precision float vector for the maximum depth of the viewport.


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setviewports.md">SetViewports</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_VIEWPORT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

