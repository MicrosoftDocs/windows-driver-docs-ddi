---
UID: NE:d3dkmdt._D3DKMDT_PIXEL_VALUE_ACCESS_MODE
title: "_D3DKMDT_PIXEL_VALUE_ACCESS_MODE"
author: windows-driver-content
description: The D3DKMDT_PIXEL_VALUE_ACCESS_MODE enumeration is used to indicate the way color values or palette indices are stored in the primary surface of a video present source.
old-location: display\d3dkmdt_pixel_value_access_mode.htm
old-project: display
ms.assetid: da4074ac-309d-46b9-b630-79d73ed73f36
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmdt/D3DKMDT_PVAM_UNINITIALIZED, d3dkmdt/D3DKMDT_PIXEL_VALUE_ACCESS_MODE, D3DKMDT_PIXEL_VALUE_ACCESS_MODE enumeration [Display Devices], D3DKMDT_PVAM_PRESETPALETTE, D3DKMDT_PIXEL_VALUE_ACCESS_MODE, D3DKMDT_PVAM_SETTABLEPALETTE, DmEnums_ac8b4715-9a7c-4698-8f57-e6125f90f75b.xml, display.d3dkmdt_pixel_value_access_mode, D3DKMDT_PVAM_UNINITIALIZED, _D3DKMDT_PIXEL_VALUE_ACCESS_MODE, d3dkmdt/D3DKMDT_PVAM_SETTABLEPALETTE, d3dkmdt/D3DKMDT_PVAM_PRESETPALETTE, d3dkmdt/D3DKMDT_PVAM_DIRECT, D3DKMDT_PVAM_DIRECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	D3DKMDT_PIXEL_VALUE_ACCESS_MODE
product: Windows
targetos: Windows
req.typenames: D3DKMDT_PIXEL_VALUE_ACCESS_MODE
---

# _D3DKMDT_PIXEL_VALUE_ACCESS_MODE enumeration


## -description


The D3DKMDT_PIXEL_VALUE_ACCESS_MODE enumeration is used to indicate the way color values or palette indices are stored in the primary surface of a video present source.


## -syntax


````
typedef enum _D3DKMDT_PIXEL_VALUE_ACCESS_MODE { 
  D3DKMDT_PVAM_UNINITIALIZED    = 0,
  D3DKMDT_PVAM_DIRECT           = 1,
  D3DKMDT_PVAM_PRESETPALETTE    = 2,
  D3DKMDT_PVAM_SETTABLEPALETTE  = 3
} D3DKMDT_PIXEL_VALUE_ACCESS_MODE;
````


## -enum-fields




### -field D3DKMDT_PVAM_UNINITIALIZED

Indicates that a variable of type D3DKMDT_PIXEL_VALUE_ACCESS_MODE has not yet been assigned a meaningful value.


### -field D3DKMDT_PVAM_DIRECT

Indicates that colors are stored directly in the primary surface.


### -field D3DKMDT_PVAM_PRESETPALETTE

Indicates that palette indices are stored in the primary surface. Colors are stored in a palette that is specific to the display adapter. The operating system can query the display miniport driver for the palette.


### -field D3DKMDT_PVAM_SETTABLEPALETTE

Indicates that palette indices are stored in the primary surface. Colors are stored in a palette that the operating system can set dynamically by calling the display miniport driver.


## -remarks


The <b>Format.Graphics</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a> structure is a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_graphics_rendering_format.md">D3DKMDT_GRAPHICS_RENDERING_FORMAT</a> structure. The <b>PixelValueAccessMode</b> member of the D3DKMDT_GRAPHICS_RENDERING_FORMAT structure is a D3DKMDT_PIXEL_VALUE_ACCESS_MODE value.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570558">VidPn Source Mode Set Interface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_PIXEL_VALUE_ACCESS_MODE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

