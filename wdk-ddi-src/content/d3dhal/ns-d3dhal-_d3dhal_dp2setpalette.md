---
UID: NS:d3dhal._D3DHAL_DP2SETPALETTE
title: "_D3DHAL_DP2SETPALETTE"
author: windows-driver-content
description: The D3DHAL_DP2SETPALETTE structure is used to associate a palette with a texture when a driver responds to D3DDP2OP_SETPALETTE in D3dDrawPrimitives2.
old-location: display\d3dhal_dp2setpalette.htm
old-project: display
ms.assetid: 8c472869-028e-41f5-93df-94e91c47b76e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*LPD3DHAL_DP2SETPALETTE, D3DHAL_DP2SETPALETTE, D3DHAL_DP2SETPALETTE structure [Display Devices], LPD3DHAL_DP2SETPALETTE, LPD3DHAL_DP2SETPALETTE structure pointer [Display Devices], _D3DHAL_DP2SETPALETTE, d3dhal/D3DHAL_DP2SETPALETTE, d3dhal/LPD3DHAL_DP2SETPALETTE, d3dstrct_da8023c8-d0a5-4793-a433-6f8860f0f11f.xml, display.d3dhal_dp2setpalette"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dhal.h
api_name:
-	D3DHAL_DP2SETPALETTE
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2SETPALETTE
---

# _D3DHAL_DP2SETPALETTE structure


## -description


The D3DHAL_DP2SETPALETTE structure is used to associate a palette with a texture when a driver responds to D3DDP2OP_SETPALETTE in <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>. This opcode is used to map an association between a palette handle and a surface handle, and specify the characteristics of the palette.


## -syntax


````
typedef struct _D3DHAL_DP2SETPALETTE {
  DWORD dwPaletteHandle;
  DWORD dwPaletteFlags;
  DWORD dwSurfaceHandle;
} D3DHAL_DP2SETPALETTE, *LPD3DHAL_DP2SETPALETTE;
````


## -struct-fields




### -field dwPaletteHandle

Specifies a handle to the palette to be set up. If the value is zero, the surface specified by <b>dwSurfaceHandle</b> should be uncoupled from any palette it might have been associated with previously.


### -field dwPaletteFlags

Specifies a set of flags that specify the attributes of the palette.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DDRAWIPAL_2

</td>
<td>
The palette has 2 entries. Currently unused.

</td>
</tr>
<tr>
<td>
DDRAWIPAL_4

</td>
<td>
The palette has 4 entries. Currently unused.

</td>
</tr>
<tr>
<td>
DDRAWIPAL_16

</td>
<td>
The palette has 16 entries. Currently unused.

</td>
</tr>
<tr>
<td>
DDRAWIPAL_256

</td>
<td>
The palette has 256 entries. Currently unused.

</td>
</tr>
<tr>
<td>
DDRAWIPAL_ALLOW256

</td>
<td>
The palette can be fully updated. Currently unused.

</td>
</tr>
<tr>
<td>
DDRAWIPAL_ALPHA

</td>
<td>
The palette's alpha data channel is valid and should be used.

</td>
</tr>
<tr>
<td>
DDRAWIPAL_DIRTY

</td>
<td>
The palette has been changed so the GDI palette is out of sync. Currently unused.

</td>
</tr>
<tr>
<td>
DDRAWIPAL_EXCLUSIVE

</td>
<td>
The palette is being used in exclusive mode. Currently unused.

</td>
</tr>
<tr>
<td>
DDRAWIPAL_GDI

</td>
<td>
The palette is allocated through GDI. Currently unused.

</td>
</tr>
<tr>
<td>
DDRAWIPAL_INHEL

</td>
<td>
The palette is done in the HEL (hardware emulation layer). Currently unused.

</td>
</tr>
<tr>
<td>
DDRAWIPAL_STORED_8

</td>
<td>
The palette is stored using 8 bpp per entry. Currently unused.

</td>
</tr>
<tr>
<td>
DDRAWIPAL_STORED_16

</td>
<td>
The palette is stored using 16 bpp per entry. Currently unused.

</td>
</tr>
<tr>
<td>
DDRAWIPAL_STORED_24

</td>
<td>
The palette is stored using 24 bpp per entry. Currently unused.

</td>
</tr>
<tr>
<td>
DDRAWIPAL_STORED_8INDEX

</td>
<td>
The palette is stored as an 8-bit index into a destination palette. Currently unused.

</td>
</tr>
</table>
 


### -field dwSurfaceHandle

Specifies a handle to the Direct3D surface (texture) that this palette (identified by <b>dwPaletteHandle</b>) is associated to.


## -remarks



The number of D3DHAL_DP2SETPALETTE structures to follow is specified by the <b>wStateCount</b> member of the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure that precedes them in the command stream.




## -see-also

D3DDP2OP_SETPALETTE



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2SETPALETTE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

