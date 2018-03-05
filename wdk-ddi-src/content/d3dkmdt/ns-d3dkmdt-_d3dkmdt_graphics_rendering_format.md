---
UID: NS:d3dkmdt._D3DKMDT_GRAPHICS_RENDERING_FORMAT
title: "_D3DKMDT_GRAPHICS_RENDERING_FORMAT"
author: windows-driver-content
description: The D3DKMDT_GRAPHICS_RENDERING_FORMAT structure contains information about a primary rendering surface.
old-location: display\d3dkmdt_graphics_rendering_format.htm
old-project: display
ms.assetid: 954cc3f6-731f-4c55-bf61-63b5d48248c0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMDT_GRAPHICS_RENDERING_FORMAT, D3DKMDT_GRAPHICS_RENDERING_FORMAT structure [Display Devices], DmStructs_c51e5886-bbd0-48a2-8be7-98d10b13fc2d.xml, _D3DKMDT_GRAPHICS_RENDERING_FORMAT, d3dkmdt/D3DKMDT_GRAPHICS_RENDERING_FORMAT, display.d3dkmdt_graphics_rendering_format
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
-	d3dkmdt.h
api_name:
-	D3DKMDT_GRAPHICS_RENDERING_FORMAT
product: Windows
targetos: Windows
req.typenames: D3DKMDT_GRAPHICS_RENDERING_FORMAT
---

# _D3DKMDT_GRAPHICS_RENDERING_FORMAT structure


## -description


The D3DKMDT_GRAPHICS_RENDERING_FORMAT structure contains information about a primary rendering surface.


## -syntax


````
typedef struct _D3DKMDT_GRAPHICS_RENDERING_FORMAT {
  D3DKMDT_2DREGION                PrimSurfSize;
  D3DKMDT_2DREGION                VisibleRegionSize;
  DWORD                           Stride;
  D3DDDIFORMAT                    PixelFormat;
  D3DKMDT_COLOR_BASIS             ColorBasis;
  D3DKMDT_PIXEL_VALUE_ACCESS_MODE PixelValueAccessMode;
} D3DKMDT_GRAPHICS_RENDERING_FORMAT;
````


## -struct-fields




### -field PrimSurfSize

A D3DKMDT_2DREGION structure that holds the size (number of pixels, both horizontal and vertical) of the surface.


### -field VisibleRegionSize

A D3DKMDT_2DREGION structure that holds the size of the visible portion of the surface.


### -field Stride

The offset, in bytes, between one scan line and the next scan line in the surface.


### -field PixelFormat

A value from the D3DDDIFORMAT enumeration that indicates the pixel format of the surface.


### -field ColorBasis

A value from the D3DKMDT_COLOR_BASIS enumeration that indicates the color basis used to encode the content of the surface.


### -field PixelValueAccessMode

A value from the D3DKMDT_PIXEL_VALUE_ACCESS_MODE enumeration that indicates the type of data (for example, direct color values or palette indexes) that are stored in the surface.


## -see-also

<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_GRAPHICS_RENDERING_FORMAT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

