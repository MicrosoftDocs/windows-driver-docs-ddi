---
UID: NS:d3dumddi._DXVADDI_VIDEOPROCESSBLTFLAGS
title: _DXVADDI_VIDEOPROCESSBLTFLAGS (d3dumddi.h)
description: The DXVADDI_VIDEOPROCESSBLTFLAGS structure identifies changes in the current destination surface from the previous destination surface.
old-location: display\dxvaddi_videoprocessbltflags.htm
tech.root: display
ms.assetid: 790a18fa-5481-432a-921b-6310a0ab78d7
ms.date: 05/10/2018
keywords: ["DXVADDI_VIDEOPROCESSBLTFLAGS structure"]
ms.keywords: DXVA2_Structs_8c40b10b-d3f4-420b-986a-455b20b01288.xml, DXVADDI_VIDEOPROCESSBLTFLAGS, DXVADDI_VIDEOPROCESSBLTFLAGS structure [Display Devices], _DXVADDI_VIDEOPROCESSBLTFLAGS, d3dumddi/DXVADDI_VIDEOPROCESSBLTFLAGS, display.dxvaddi_videoprocessbltflags
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
req.typenames: DXVADDI_VIDEOPROCESSBLTFLAGS
f1_keywords:
 - _DXVADDI_VIDEOPROCESSBLTFLAGS
 - d3dumddi/_DXVADDI_VIDEOPROCESSBLTFLAGS
 - DXVADDI_VIDEOPROCESSBLTFLAGS
 - d3dumddi/DXVADDI_VIDEOPROCESSBLTFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - DXVADDI_VIDEOPROCESSBLTFLAGS
---

# _DXVADDI_VIDEOPROCESSBLTFLAGS structure


## -description

The DXVADDI_VIDEOPROCESSBLTFLAGS structure identifies changes in the current destination surface from the previous destination surface.

## -struct-fields

### -field BackgroundChanged

A UINT value that specifies whether the background color of the destination surface changed. Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).

### -field TargetRectChanged

A UINT value that specifies whether the target rectangle of the destination surface changed. Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).

### -field ColorDataChanged

A UINT value that specifies whether format information for the destination surface changed. Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).

### -field AlphaChanged

A UINT value that specifies whether the planar alpha value for the destination surface changed. Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the fifth through sixteenth bits (0x0000FFF0) of the 32-bit <b>Value</b> member to zeros.

### -field DestData

A UINT value that contains video processor sample destination data. Setting this member is equivalent to setting the seventeenth through thirty-second bits (0xFFFF0000) of the 32-bit <b>Value</b> member. The following bits can be set:

DXVADDI_DESTDATA_RFF (0x0001)

DXVADDI_DESTDATA_TFF (0x0002)

DXVADDI_DESTDATA_RFF_TFF_PRESENT (0x0004)

### -field Value

A 32-bit value that identifies changes in the current destination surface from the previous destination surface.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_videoprocessblt">D3DDDIARG_VIDEOPROCESSBLT</a>