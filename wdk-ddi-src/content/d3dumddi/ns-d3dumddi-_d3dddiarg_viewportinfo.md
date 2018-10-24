---
UID: NS:d3dumddi._D3DDDIARG_VIEWPORTINFO
title: "_D3DDDIARG_VIEWPORTINFO"
author: windows-driver-content
description: The D3DDDIARG_VIEWPORTINFO structure describes the location and size of a view-clipping rectangle.
old-location: display\d3dddiarg_viewportinfo.htm
tech.root: display
ms.assetid: 37e69980-fb3a-4abe-a76b-b2bd6827ae64
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_VIEWPORTINFO, D3DDDIARG_VIEWPORTINFO structure [Display Devices], UMDisplayDriver_param_Structs_ece888d8-61e4-4e7f-b052-c6e0169a6a97.xml, _D3DDDIARG_VIEWPORTINFO, d3dumddi/D3DDDIARG_VIEWPORTINFO, display.d3dddiarg_viewportinfo
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_VIEWPORTINFO
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_VIEWPORTINFO
---

# _D3DDDIARG_VIEWPORTINFO structure


## -description


The D3DDDIARG_VIEWPORTINFO structure describes the location and size of a view-clipping rectangle. 


## -struct-fields




### -field X

[in] The x coordinate, in screen coordinates, for the upper-left corner of the view-clipping rectangle.


### -field Y

[in] The y coordinate, in screen coordinates, for the upper-left corner of the view-clipping rectangle.


### -field Width

[in] The width, in screen coordinates, of the view-clipping rectangle where the application is rendering.


### -field Height

[in] The height, in screen coordinates, of the view-clipping rectangle where the application is rendering.


## -remarks



The user-mode display driver's <a href="https://msdn.microsoft.com/ef0847a3-d4f5-4a9e-a041-1b8f8523fdf7">SetViewport</a> function should update the viewport portion of its internal rendering context with the location and size values that are specified in the D3DDDIARG_VIEWPORTINFO structure. The driver can use this information to perform guard band clipping.




## -see-also




<a href="https://msdn.microsoft.com/ef0847a3-d4f5-4a9e-a041-1b8f8523fdf7">SetViewport</a>
 

 

