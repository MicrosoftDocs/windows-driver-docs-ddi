---
UID: NS:d3dumddi._D3DDDI_COLORFILLFLAGS
title: _D3DDDI_COLORFILLFLAGS (d3dumddi.h)
description: The D3DDDI_COLORFILLFLAGS structure describes how to color-fill a rectangle on a surface.
old-location: display\d3dddi_colorfillflags.htm
tech.root: display
ms.assetid: 672baa43-7fa1-4c10-9d60-c7c8a4729f26
ms.date: 05/10/2018
keywords: ["D3DDDI_COLORFILLFLAGS structure"]
ms.keywords: D3DDDI_COLORFILLFLAGS, D3DDDI_COLORFILLFLAGS structure [Display Devices], D3D_other_Structs_555ecebb-bdd8-4c7f-97cd-801216506b9e.xml, _D3DDDI_COLORFILLFLAGS, d3dumddi/D3DDDI_COLORFILLFLAGS, display.d3dddi_colorfillflags
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
req.typenames: D3DDDI_COLORFILLFLAGS
f1_keywords:
 - _D3DDDI_COLORFILLFLAGS
 - d3dumddi/_D3DDDI_COLORFILLFLAGS
 - D3DDDI_COLORFILLFLAGS
 - d3dumddi/D3DDDI_COLORFILLFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDI_COLORFILLFLAGS
---

# _D3DDDI_COLORFILLFLAGS structure


## -description

The D3DDDI_COLORFILLFLAGS structure describes how to color-fill a rectangle on a surface.

## -struct-fields

### -field PresentToDwm

A UINT value that specifies whether the Microsoft Direct3D runtime begins and ends a desktop window manager (DWM) present operation during the color-fill operation. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.

### -field Value

A member in the union that is contained in D3DDDI_COLORFILLFLAGS that can hold one 32-bit value that identifies how to color-fill a rectangle on a surface.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_colorfill">ColorFill</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_colorfill">D3DDDIARG_COLORFILL</a>

