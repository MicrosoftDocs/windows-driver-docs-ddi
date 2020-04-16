---
UID: NS:d3dhal._D3DHAL_DP2SETPALETTE
title: _D3DHAL_DP2SETPALETTE (d3dhal.h)
description: The D3DHAL_DP2SETPALETTE structure is used to associate a palette with a texture when a driver responds to D3DDP2OP_SETPALETTE in D3dDrawPrimitives2.
old-location: display\d3dhal_dp2setpalette.htm
tech.root: display
ms.assetid: 8c472869-028e-41f5-93df-94e91c47b76e
ms.date: 05/10/2018
keywords: ["_D3DHAL_DP2SETPALETTE structure"]
ms.keywords: "*LPD3DHAL_DP2SETPALETTE, D3DHAL_DP2SETPALETTE, D3DHAL_DP2SETPALETTE structure [Display Devices], LPD3DHAL_DP2SETPALETTE, LPD3DHAL_DP2SETPALETTE structure pointer [Display Devices], _D3DHAL_DP2SETPALETTE, d3dhal/D3DHAL_DP2SETPALETTE, d3dhal/LPD3DHAL_DP2SETPALETTE, d3dstrct_da8023c8-d0a5-4793-a433-6f8860f0f11f.xml, display.d3dhal_dp2setpalette"
f1_keywords:
 - "d3dhal/D3DHAL_DP2SETPALETTE"
req.header: d3dhal.h
req.include-header: D3dhal.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dhal.h
api_name:
- D3DHAL_DP2SETPALETTE
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2SETPALETTE
---

# _D3DHAL_DP2SETPALETTE structure


## -description


The D3DHAL_DP2SETPALETTE structure is used to associate a palette with a texture when a driver responds to D3DDP2OP_SETPALETTE in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>. This opcode is used to map an association between a palette handle and a surface handle, and specify the characteristics of the palette.


## -struct-fields




### -field dwPaletteHandle

Specifies a handle to the palette to be set up. If the value is zero, the surface specified by <b>dwSurfaceHandle</b> should be uncoupled from any palette it might have been associated with previously.


### -field dwPaletteFlags

Specifies a set of flags that specify the attributes of the palette.
|Flag|Meaning|
|--- |--- |
|DDRAWIPAL_2|The palette has 2 entries. Currently unused.|
|DDRAWIPAL_4|The palette has 4 entries. Currently unused.|
|DDRAWIPAL_16|The palette has 16 entries. Currently unused.|
|DDRAWIPAL_256|The palette has 256 entries. Currently unused.|
|DDRAWIPAL_ALLOW256|The palette can be fully updated. Currently unused.|
|DDRAWIPAL_ALPHA|The palette's alpha data channel is valid and should be used.|
|DDRAWIPAL_DIRTY|The palette has been changed so the GDI palette is out of sync. Currently unused.|
|DDRAWIPAL_EXCLUSIVE|The palette is being used in exclusive mode. Currently unused.|
|DDRAWIPAL_GDI|The palette is allocated through GDI. Currently unused.|
|DDRAWIPAL_INHEL|The palette is done in the HEL (hardware emulation layer). Currently unused.|
|DDRAWIPAL_STORED_8|The palette is stored using 8 bpp per entry. Currently unused.|
|DDRAWIPAL_STORED_16|The palette is stored using 16 bpp per entry. Currently unused.|
|DDRAWIPAL_STORED_24|The palette is stored using 24 bpp per entry. Currently unused.|
|DDRAWIPAL_STORED_8INDEX|The palette is stored as an 8-bit index into a destination palette. Currently unused.|


### -field dwSurfaceHandle

Specifies a handle to the Direct3D surface (texture) that this palette (identified by <b>dwPaletteHandle</b>) is associated to.


## -remarks



The number of D3DHAL_DP2SETPALETTE structures to follow is specified by the <b>wStateCount</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a> structure that precedes them in the command stream.




## -see-also




D3DDP2OP_SETPALETTE



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

