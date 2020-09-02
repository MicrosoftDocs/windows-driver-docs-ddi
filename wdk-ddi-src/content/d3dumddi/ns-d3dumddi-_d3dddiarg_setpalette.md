---
UID: NS:d3dumddi._D3DDDIARG_SETPALETTE
title: _D3DDDIARG_SETPALETTE (d3dumddi.h)
description: The D3DDDIARG_SETPALETTE structure describes how to associate a palette with a texture.
old-location: display\d3dddiarg_setpalette.htm
tech.root: display
ms.assetid: 265912e2-2076-4435-811f-70a3dd1a0bd7
ms.date: 05/10/2018
keywords: ["D3DDDIARG_SETPALETTE structure"]
ms.keywords: D3DDDIARG_SETPALETTE, D3DDDIARG_SETPALETTE structure [Display Devices], UMDisplayDriver_param_Structs_6fb950bf-0a0f-4d87-950d-7030251ed074.xml, _D3DDDIARG_SETPALETTE, d3dumddi/D3DDDIARG_SETPALETTE, display.d3dddiarg_setpalette
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
targetos: Windows
req.typenames: D3DDDIARG_SETPALETTE
f1_keywords:
 - _D3DDDIARG_SETPALETTE
 - d3dumddi/_D3DDDIARG_SETPALETTE
 - D3DDDIARG_SETPALETTE
 - d3dumddi/D3DDDIARG_SETPALETTE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_SETPALETTE
---

# _D3DDDIARG_SETPALETTE structure


## -description

The D3DDDIARG_SETPALETTE structure describes how to associate a palette with a texture.

## -struct-fields

### -field PaletteHandle

[in] A handle to the palette to be set up. If the value of <b>PaletteHandle</b> is zero, the surface that is specified by <b>hResource</b> should be uncoupled from any palette that it might have been associated with previously.

### -field PaletteFlags

[in] A valid bitwise OR of the following flags that specify the attributes of the palette.

| **Flag** | **Meaning** | 
|:--|:--|
| D3DDDISETPALETTE_256 (0x00000001) | The palette has 256 entries. | 
| D3DDDISETPALETTE_ALLOW256 (0x00000200) | The palette can be fully updated. | 
| D3DDDISETPALETTE_ALPHA (0x00002000) | The palette's alpha data channel is valid and should be used. |

### -field hResource

[in] A handle to the surface (texture) with which the palette that is identified by <b>PaletteHandle</b> is associated.

## -remarks

The user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setpalette">SetPalette</a> function associates the palette that is specified by the <b>PaletteHandle</b> member with the surface that is specified by the <b>hResource</b> member and uses the <b>PaletteFlags</b> member to specify the characteristics of the palette.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setpalette">SetPalette</a>

