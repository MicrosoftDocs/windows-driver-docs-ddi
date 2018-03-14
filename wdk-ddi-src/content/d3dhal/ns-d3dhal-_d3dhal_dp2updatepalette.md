---
UID: NS:d3dhal._D3DHAL_DP2UPDATEPALETTE
title: "_D3DHAL_DP2UPDATEPALETTE"
author: windows-driver-content
description: The D3DHAL_DP2UPDATEPALETTE structure alters the palette that is used for palletized textures.
old-location: display\d3dhal_dp2updatepalette.htm
old-project: display
ms.assetid: 1ab2e4da-1107-4a5b-99e4-9c9ea864f95e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_DP2UPDATEPALETTE, D3DHAL_DP2UPDATEPALETTE, D3DHAL_DP2UPDATEPALETTE structure [Display Devices], LPD3DHAL_DP2UPDATEPALETTE, LPD3DHAL_DP2UPDATEPALETTE structure pointer [Display Devices], _D3DHAL_DP2UPDATEPALETTE, d3dhal/D3DHAL_DP2UPDATEPALETTE, d3dhal/LPD3DHAL_DP2UPDATEPALETTE, d3dstrct_93a9e991-e818-4dd0-a101-779baa0a873d.xml, display.d3dhal_dp2updatepalette"
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
-	D3DHAL_DP2UPDATEPALETTE
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2UPDATEPALETTE
---

# _D3DHAL_DP2UPDATEPALETTE structure


## -description


The D3DHAL_DP2UPDATEPALETTE structure alters the palette that is used for palletized textures.


## -syntax


````
typedef struct _D3DHAL_DP2UPDATEPALETTE {
  DWORD dwPaletteHandle;
  WORD  wStartIndex;
  WORD  wNumEntries;
} D3DHAL_DP2UPDATEPALETTE, *LPD3DHAL_DP2UPDATEPALETTE;
````


## -struct-fields




### -field dwPaletteHandle

Specifies a handle to the palette to be altered.


### -field wStartIndex

Specifies the index in the palette beyond which data is updated. 


### -field wNumEntries

Specifies the number of PALETTEENTRYs being updated.


## -remarks



The D3DHAL_DP2UPDATEPALETTE structure is used when responding to the D3DDP2OP_UPDATEPALETTE opcode in <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>. 

The palette handle attached to a surface is updated with <b>wNumEntries</b> PALETTEENTRYs starting at a specific <b>wStartIndex</b> member of the palette. A PALETTEENTRY (defined in <i>wingdi.h</i> and <i>wtypes.h</i>) is actually a DWORD with an ARGB color for each byte.

After the D3DHAL_DP2UPDATEPALETTE structure in the command stream, the actual palette data follows (without any padding), consisting of one DWORD per palette entry (in ARGB format, with 8 bits for each of the four channels). There is only one D3DHAL_DP2UPDATEPALETTE structure (plus palette data) following the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure regardless of the value of <b>wStateCount</b> (a member of the D3DHAL_DP2COMMAND structure).




## -see-also

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



D3DDP2OP_UPDATEPALETTE



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



 

 


