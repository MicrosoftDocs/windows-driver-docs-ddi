---
UID: NS:d3dkmdt._DXGKARG_SETPALETTE
title: _DXGKARG_SETPALETTE (d3dkmdt.h)
description: The DXGKARG_SETPALETTE structure describes the palette to set for a display.
old-location: display\dxgkarg_setpalette.htm
tech.root: display
ms.assetid: a76d9549-d182-437f-a570-7d24fd6a5488
ms.date: 05/10/2018
ms.keywords: DXGKARG_SETPALETTE, DXGKARG_SETPALETTE structure [Display Devices], DmStructs_d5720608-bc3d-437a-b080-6cd8b9635391.xml, _DXGKARG_SETPALETTE, d3dkmdt/DXGKARG_SETPALETTE, display.dxgkarg_setpalette
ms.topic: struct
f1_keywords:
 - "d3dkmdt/DXGKARG_SETPALETTE"
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
- DXGKARG_SETPALETTE
product:
- Windows
targetos: Windows
req.typenames: DXGKARG_SETPALETTE
---

# _DXGKARG_SETPALETTE structure


## -description


The DXGKARG_SETPALETTE structure describes the palette to set for a display. 


## -struct-fields




### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the palette is set on. 


### -field FirstEntry

[in] The location in the device palette that the first entry in the array of color entries that <b>pLookupTable</b> specifies is copied to. The remaining entries that <b>pLookupTable</b> specifies are copied sequentially, from this starting point into the device's palette.


### -field NumEntries

[in] The number of color entries in the array that <b>pLookupTable</b> specifies.


### -field pLookupTable

[in] An array of color entries to copy into the device's color palette (that is, the device's color registers). Each color entry is accessed as a generic 32-bit value or as the <b>Red</b>, <b>Green</b>, <b>Blue</b>, and <b>Unused</b> members of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_palettedata">D3DKMDT_PALETTEDATA</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_palettedata">D3DKMDT_PALETTEDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_setpalette">DxgkDdiSetPalette</a>
 

 

