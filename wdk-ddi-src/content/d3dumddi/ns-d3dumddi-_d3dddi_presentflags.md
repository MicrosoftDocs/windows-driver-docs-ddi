---
UID: NS:d3dumddi._D3DDDI_PRESENTFLAGS
title: _D3DDDI_PRESENTFLAGS (d3dumddi.h)
description: The D3DDDI_PRESENTFLAGS structure identifies how to perform a present operation.
old-location: display\d3dddi_presentflags.htm
tech.root: display
ms.assetid: adab4c0f-b879-409c-97a3-f161a50514f5
ms.date: 05/10/2018
ms.keywords: D3DDDI_PRESENTFLAGS, D3DDDI_PRESENTFLAGS structure [Display Devices], D3D_other_Structs_4650db5e-637b-4032-a5d2-ded887a883dc.xml, _D3DDDI_PRESENTFLAGS, d3dumddi/D3DDDI_PRESENTFLAGS, display.d3dddi_presentflags
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
- D3DDDI_PRESENTFLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_PRESENTFLAGS
---

# _D3DDDI_PRESENTFLAGS structure


## -description


The D3DDDI_PRESENTFLAGS structure identifies how to perform a present operation.


## -struct-fields




### -field Blt

A UINT value that specifies whether to perform a bit-block transfer (bitblt) data to the primary surface. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field ColorFill

A UINT value that specifies whether to perform a colorfill bitblt to the primary surface . 

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field Flip

A UINT value that specifies whether to flip to a new surface. 

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field AllowTearing

 


### -field AllowFlexibleRefresh

 


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 29 bits (0xFFFFFFF8) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that is contained in D3DDDI_PRESENTFLAGS that can hold one 32-bit value that identifies how to perform a present operation.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543240">D3DDDIARG_PRESENT</a>



<a href="https://msdn.microsoft.com/e90683b4-64b6-4018-96a5-b50118df3367">Present</a>
 

 

