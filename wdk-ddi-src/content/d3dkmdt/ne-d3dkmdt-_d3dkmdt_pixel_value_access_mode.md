---
UID: NE:d3dkmdt._D3DKMDT_PIXEL_VALUE_ACCESS_MODE
title: _D3DKMDT_PIXEL_VALUE_ACCESS_MODE (d3dkmdt.h)
description: The D3DKMDT_PIXEL_VALUE_ACCESS_MODE enumeration is used to indicate the way color values or palette indices are stored in the primary surface of a video present source.
old-location: display\d3dkmdt_pixel_value_access_mode.htm
tech.root: display
ms.assetid: da4074ac-309d-46b9-b630-79d73ed73f36
ms.date: 05/10/2018
ms.keywords: D3DKMDT_PIXEL_VALUE_ACCESS_MODE, D3DKMDT_PIXEL_VALUE_ACCESS_MODE enumeration [Display Devices], D3DKMDT_PVAM_DIRECT, D3DKMDT_PVAM_PRESETPALETTE, D3DKMDT_PVAM_SETTABLEPALETTE, D3DKMDT_PVAM_UNINITIALIZED, DmEnums_ac8b4715-9a7c-4698-8f57-e6125f90f75b.xml, _D3DKMDT_PIXEL_VALUE_ACCESS_MODE, d3dkmdt/D3DKMDT_PIXEL_VALUE_ACCESS_MODE, d3dkmdt/D3DKMDT_PVAM_DIRECT, d3dkmdt/D3DKMDT_PVAM_PRESETPALETTE, d3dkmdt/D3DKMDT_PVAM_SETTABLEPALETTE, d3dkmdt/D3DKMDT_PVAM_UNINITIALIZED, display.d3dkmdt_pixel_value_access_mode
f1_keywords:
 - "d3dkmdt/D3DKMDT_PIXEL_VALUE_ACCESS_MODE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmdt.h
api_name:
- D3DKMDT_PIXEL_VALUE_ACCESS_MODE
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_PIXEL_VALUE_ACCESS_MODE
---

# _D3DKMDT_PIXEL_VALUE_ACCESS_MODE enumeration


## -description


The D3DKMDT_PIXEL_VALUE_ACCESS_MODE enumeration is used to indicate the way color values or palette indices are stored in the primary surface of a video present source.


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



The <b>Format.Graphics</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a> structure is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_graphics_rendering_format">D3DKMDT_GRAPHICS_RENDERING_FORMAT</a> structure. The <b>PixelValueAccessMode</b> member of the D3DKMDT_GRAPHICS_RENDERING_FORMAT structure is a D3DKMDT_PIXEL_VALUE_ACCESS_MODE value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">VidPn Source Mode Set Interface</a>
 

 

