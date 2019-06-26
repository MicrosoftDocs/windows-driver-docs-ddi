---
UID: NS:d3dumddi._D3DDDI_FLIPOVERLAYFLAGS
title: _D3DDDI_FLIPOVERLAYFLAGS (d3dumddi.h)
description: The D3DDDI_FLIPOVERLAYFLAGS structure identifies how to flip a resource on an overlay.
old-location: display\d3dddi_flipoverlayflags.htm
tech.root: display
ms.assetid: 09146e6b-3ac0-422a-addb-831394a15c08
ms.date: 05/10/2018
ms.keywords: D3DDDI_FLIPOVERLAYFLAGS, D3DDDI_FLIPOVERLAYFLAGS structure [Display Devices], D3D_other_Structs_a62b399d-d553-4325-9f5a-ceb08287d4f4.xml, _D3DDDI_FLIPOVERLAYFLAGS, d3dumddi/D3DDDI_FLIPOVERLAYFLAGS, display.d3dddi_flipoverlayflags
ms.topic: struct
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
- D3DDDI_FLIPOVERLAYFLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_FLIPOVERLAYFLAGS
---

# _D3DDDI_FLIPOVERLAYFLAGS structure


## -description


The D3DDDI_FLIPOVERLAYFLAGS structure identifies how to flip a resource on an overlay.


## -struct-fields




### -field Even

A UINT value that specifies whether the interleaved field to be displayed is even. The <b>Even</b> bit-field is set when the overlay is requested to deinterlace the data.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Odd

A UINT value that specifies whether the interleaved field to be displayed is odd. The <b>Odd</b> bit-field is set when the overlay is requested to deinterlace the data.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that is contained in D3DDDI_FLIPOVERLAYFLAGS that can hold one 32-bit value that identifies how to flip a resource on an overlay.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_flipoverlay">D3DDDIARG_FLIPOVERLAY</a>
 

 

