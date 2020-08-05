---
UID: NS:d3dumddi._DXVADDI_VIDEOSAMPLEFLAGS
title: _DXVADDI_VIDEOSAMPLEFLAGS (d3dumddi.h)
description: The DXVADDI_VIDEOSAMPLEFLAGS structure identifies changes in the current sample frame from the previous sample frame.
old-location: display\dxvaddi_videosampleflags.htm
tech.root: display
ms.assetid: 1dca2b12-0542-43a9-abff-203ea34cff90
ms.date: 05/10/2018
keywords: ["DXVADDI_VIDEOSAMPLEFLAGS structure"]
ms.keywords: DXVA2_Structs_8e0fce9f-8473-4bbc-9403-fb8755090a7d.xml, DXVADDI_VIDEOSAMPLEFLAGS, DXVADDI_VIDEOSAMPLEFLAGS structure [Display Devices], _DXVADDI_VIDEOSAMPLEFLAGS, d3dumddi/DXVADDI_VIDEOSAMPLEFLAGS, display.dxvaddi_videosampleflags
f1_keywords:
 - "d3dumddi/DXVADDI_VIDEOSAMPLEFLAGS"
 - "DXVADDI_VIDEOSAMPLEFLAGS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- DXVADDI_VIDEOSAMPLEFLAGS
targetos: Windows
req.typenames: DXVADDI_VIDEOSAMPLEFLAGS
---

# _DXVADDI_VIDEOSAMPLEFLAGS structure


## -description


The DXVADDI_VIDEOSAMPLEFLAGS structure identifies changes in the current sample frame from the previous sample frame.


## -struct-fields




### -field PaletteChanged

A UINT value that specifies whether the palette of the sample frame changed. Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field SrcRectChanged

A UINT value that specifies whether the source rectangle of the sample frame changed. Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field DstRectChanged

A UINT value that specifies whether the destination rectangle of the sample frame changed. Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field ColorDataChanged

A UINT value that specifies whether the color data of the sample frame changed. Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field PlanarAlphaChanged

A UINT value that specifies whether the alpha (transparency) data of the sample frame changed. Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the sixth through sixteenth bits (0x0000FFE0) of the 32-bit <b>Value</b> member to zeros.


### -field SampleData

A UINT value that contains video sample data. Setting this member is equivalent to setting the seventeenth through thirty-second bits (0xFFFF0000) of the 32-bit <b>Value</b> member. The following bits can be set:

DXVADDI_SAMPLEDATA_RFF (0x0001)

DXVADDI_SAMPLEDATA_TFF (0x0002)

DXVADDI_SAMPLEDATA_RFF_TFF_PRESENT (0x0004) 


### -field Value

A member in the union that is contained in DXVADDI_VIDEOSAMPLEFLAGS that can hold one 32-bit value that identifies changes in the current sample frame from the previous sample frame.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_videosample">DXVADDI_VIDEOSAMPLE</a>
 

 

